import requests
import threading
from bitcoin.main import *

def database():
    #url of bitcoin address balance
    try:
        url = 'https://blockchain.info/es/q/addressbalance/{address}?confirmations=6'
    except:
        url = 'https://blockexplorer.com/api/addr/{address}/balance'

    while True:
        #generator bitcoin wallet
        key = random_key()
        pub = privtopub(key)
        addr = pubtoaddr(pub)
        balance = requests.get(url=url.format(address=addr)).text

        print(key, addr, balance)
        
        if int(balance) > 0:
    	    with open('databitcoin.txt', 'a') as f:
    		    f.write(key+'\t'+addr+'\t'+balance+'\n')
    		    f.close()
    		    break;


if __name__ == '__main__':

    th = threading.Thread(target=database)
    th.run()
