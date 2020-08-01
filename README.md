# Setting up and starting your network 
---
First you will need to get the environments and dependencies that you need which are:
* Geth
* Puppeth
* MyCrypto

Then using geth you want to create your node's data directory and create your passwords using the following code
* ./geth account new --datadir node1
* ./geth account new --datadir node2

Once you have that set you want to run ./puppeth and create your network and create your new genesis block. After you are done it should look like this:

![](Screenshots/Screenshot (7).png)

Now its time to initialize each node with your network name with this code:
* ./geth init yournetworkname.json --datadir node1/
* ./geth init yournetworkname.json --datadir node2/

Now you want to run your first node running this code in one of your terminals:
* ./geth --datadir node1/ --syncmode 'full' --networkid (any_numbers) --rpc --minerthreads 1 --unlock "node1_sealer_address" --password node1/password.txt --mine --allow-insecure-unlock

Then run this code in your other terminal for your second node:
* ./geth --datadir node2/ --syncmode 'full' --networkid (any_numbers) --unlock "node2_sealer_address" --password node2/password.txt --mine --allow-insecure-unlock --port 30304 --bootnodes "enode_address_from_node1" --ipcdisable

Your nodes should now be running and producing new blocks and should look something like this:

![](Screenshot (10).png)

Now you want to connect to MyCrypto and add a custom node and set it up with the information you did in the beginning. Once inside you should see ALOT of ETH in your account. You want to now put in your second node address and send it some ETH. When you send your transaction you should see a confirmation page like this:

![](Screenshot (11).png)

Now you are a blockchain master! 