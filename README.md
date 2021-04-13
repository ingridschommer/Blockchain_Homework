# Blockchain Homework

In order to create accounts for two nodes for the network with a separate datadir for each using geth, I followed the step by step PoA Guide. 

I accessed the terminal in my geth folder and ran the following commands: 
- ./geth --datadir node1 account new
- ./geth --datadir node2 account new

Once these nodes were set up, I created a genesis block using puppeth.

![Configure new Genesis](https://github.com/ingridschommer/Blockchain_Homework/blob/main/Screenshots/Configure%20new%20Genesis.png)


Once the genesis block was created, I initialized the nodes with the genesis' json file by running the following commands: 
- ./geth --datadir node1 init networkname.json
- ./geth --datadir node2 init networkname.json


Once those initialized successfully, I ran the following commands in order to run the nodes (in seperate terminals)
- ./geth --datadir node1 --unlock "SEALER_ONE_ADDRESS" --mine --rpc --allow-insecure-unlock
- ./geth --datadir node2 --unlock "SEALER_TWO_ADDRESS" --mine --port 30304 --bootnodes "enode://SEALER_ONE_ENODE_ADDRESS@127.0.0.1:30303" --ipcdisable --allow-insecure-unlock

My private PoA block was now running successfully. 

Next, I opened MyCrypto in order to send ETH from node1 to node2. 
