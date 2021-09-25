# Blockchain-Homework
## Background
I have landed a new job at ZBank, a small, innovative bank that is interested in exploring what block chain technology can do for them and their customers. My first project at the company is to set up a private test net that my team of developers can use to explore potentials for block chain at ZBank. I have decided on setting up a test net because:
1.	There is no real money involved, which will give your team of developers the freedom to experiment.
2.	Test nets *allows* for offline development.
Tokens inherently have no value here, so we will provide pre-configured accounts and nodes for easy setup.

![MyCrypto](https://user-images.githubusercontent.com/83382006/134716219-a543c1ed-060b-470b-87a6-905891c67534.png)

Once you download the installer, open and follow the installation wizard’s commands.

** There will be a tutorial available when you first open the program; it is strongly advised to not skip through it. 
On the initial download there may be security alerts advising you that it is an unidentified application. You should be prompted to allow the download regardless.

## GO ETHEREUM
Next we’ll be installing Go Ethereum:
1.	Using this link https://geth.ethereum.org/downloads/ open a new tab in your browser and scroll down to “Stable Releases.”
2.	Please install ‘Geth & tools 1.9.7’. This is version specific, any other version ***WILL NOT*** work. 

![image](https://user-images.githubusercontent.com/83382006/134761513-0c74c46e-91f6-4a44-afab-9f63e1083c8c.png)


a.	You need to know if you’re running a 32 bit operating system or a 64 bit. This information can be found in your settings folder. 
3.	After downloading the tools archive, open your "Downloads" folder, and you will find a file named geth-alltools-darwin-amd64-1.9.7-a718daa6.tar.gz in OS X, and a file called geth-alltools-windows-amd64-1.9.7-a718daa6.zip in Windows. Note that the last numbers in the filename could vary depending on the last build available.
4.	Decompress the archive in the location of your preference on your computer's hard drive, and rename the containing folder as Blockchain-Tools. We recommend using a location that can be easily accessed from the terminal window like the user's home directory.


*Great now that everything is installed and running, let’s begin shall we?*
Open up your MyCrypto application and begin the login portion. 
![image](https://user-images.githubusercontent.com/83382006/134774553-ef595b18-3aa2-4cc5-b441-a5cfcd929668.png)

in the bottom left had portion you'll see mnemonic phrase. click on that and save the text in a text document, it will ask you to choose those words in order to unlock the wallet. 

Once that's completed, choose an address for your wallet and save the address in the same note pad file. 


![image](https://user-images.githubusercontent.com/83382006/134775225-081cd49a-fa62-4489-9268-c23e8ab4e6b0.png)


![image](https://user-images.githubusercontent.com/83382006/134775250-9954a707-0292-483f-ab65-5b318bd949f7.png)

it should look like this once you're in.

![image](https://user-images.githubusercontent.com/83382006/134777099-807c5b09-bce1-47a6-8604-5bb8f33d8816.png)


Opening up your gitbash go into your blockchain folder that you created and type in ./geth --datadir node1 account new
it will give you a new address and secret keystore path. These also need to be saved in the note pad..

![image](https://user-images.githubusercontent.com/83382006/134777624-c1dcd217-4925-48eb-a4ef-b33cc45291e5.png)

Now we'll make the Genesis from scratch. This will create a network in your MyCrypto for you to connect to and it will link the two nodes that we just created. 
We do thiis so you can send test money between the two nodes. 

**How to set up a genesis block:**
1.	Download my crypto
2.	Download geth
3.	Using gitbash go Into blockchain directory
4.	Open MyCrypto and make sure the Ropsten network is available. 
5.	Open my Crypto, choose wallet info
6.	Input mnemonic phrase and choose address
7.	Once you’ve signed in, using the drop down menu choose wallet information.
8.	You have a private key available to you. The same notepad that you saved your mnemonic phrase and address in, save your private key. 
9.	Going back to gitbash and in your block chain folder type in command ./puppet
10.	Name this network, something you’ll remember, then choose option 2 (configure a new genesis)

  a.	Then create genesis from scratch (option 1)
  
  b.	Consensus engine is proof of work (option 1)
  
  c.	Then put in your wallet address without adding in the 0x
  
  d.	You’ll see an option to add another address, hit enter to ignore
  
  e.	Now you’ll see a question come up saying should the address be funded with wei, hit enter to ignore. 
  
  f.	Make network id 333
  
  g. Now we manage (2) and export the genesis (2).
  (don't worry if you're a little lost all the steps are shown in the picture in the bottom)

![image](https://user-images.githubusercontent.com/83382006/134777739-9c50f7b8-f2f9-4d18-86a4-79c6667d9b3f.png)

![image](https://user-images.githubusercontent.com/83382006/134777810-a9cbdfa5-7c0f-4fcb-abcc-aa41a27e6a4a.png)
![image](https://user-images.githubusercontent.com/83382006/134777838-b778603c-448f-4621-b96b-666eb3c5fa2f.png)

## Now we'll create your POA
The Proof of Authority (PoA) algorithm is typically used for private blockchain networks as it requires pre-approval of, or voting in of, the account addresses that can approve transactions (seal blocks).


Because the accounts must be approved, we will generate two new nodes with new account addresses that will serve as our pre-approved sealer addresses.

Create accounts for two nodes for the network with a separate datadir for each using geth.

./geth --datadir node1 account new
./geth --datadir node2 account new





Next, generate your genesis block.


Run puppeth, name your network, and select the option to configure a new genesis block.


Choose the Clique (Proof of Authority) consensus algorithm.


Paste both account addresses from the first step one at a time into the list of accounts to seal.


Paste them again in the list of accounts to pre-fund. There are no block rewards in PoA, so you'll need to pre-fund.


You can choose no for pre-funding the pre-compiled accounts (0x1 .. 0xff) with wei. This keeps the genesis cleaner.


Complete the rest of the prompts, and when you are back at the main menu, choose the "Manage existing genesis" option.


Export genesis configurations. This will fail to create two of the files, but you only need networkname.json.




With the genesis block creation completed, we will now initialize the nodes with the genesis' json file.

Using geth, initialize each node with the new networkname.json.

./geth --datadir node1 init networkname.json
./geth --datadir node2 init networkname.json





Now the nodes can be used to begin mining blocks.

Run the nodes in separate terminal windows with the commands:

./geth --datadir node1 --unlock "SEALER_ONE_ADDRESS" --mine --rpc --allow-insecure-unlock
./geth --datadir node2 --unlock "SEALER_TWO_ADDRESS" --mine --port 30304 --bootnodes "enode://SEALER_ONE_ENODE_ADDRESS@127.0.0.1:30303" --ipcdisable --allow-insecure-unlock



NOTE: Type your password and hit enter - even if you can't see it visually!



Your private PoA blockchain should now be running!


With both nodes up and running, the blockchain can be added to MyCrypto for testing.

Open the MyCrypto app, then click Change Network at the bottom left:
![image](https://user-images.githubusercontent.com/83382006/134780860-c02db89c-a2e3-4b88-8c99-1dd853ecafa4.png)



Click "Add Custom Node", then add the custom network information that you set in the genesis.


Make sure that you scroll down to choose Custom in the "Network" column to reveal more options like Chain ID:

![image](https://user-images.githubusercontent.com/83382006/134780727-894c93a8-9e50-4830-b397-b3aaf9c3db4c.png)

Type ETH in the Currency box.


In the Chain ID box, type the chain id you generated during genesis creation.


In the URL box type: http://127.0.0.1:8545.  This points to the default RPC port on your local machine.


Finally, click Save & Use Custom Node.




After connecting to the custom network in MyCrypto, it can be tested by sending money between accounts.

Select the View & Send option from the left menu pane, then click Keystore file.

![image](https://user-images.githubusercontent.com/83382006/134780903-af891a17-24c5-49b8-9844-fc69f8833e29.png)

On the next screen, click Select Wallet File, then navigate to the keystore directory inside your Node1 directory, select the file located there, provide your password when prompted and then click Unlock.


This will open your account wallet inside MyCrypto.


Looks like we're filthy rich! This is the balance that was pre-funded for this account in the genesis configuration; however, these millions of ETH tokens are just for testing purposes.

In the To Address box, type the account address from Node2, then fill in an arbitrary amount of ETH.

Confirm the transaction by clicking "Send Transaction", and the "Send" button in the pop-up window.

Click the Check TX Status when the green message pops up, confirm the logout:

You should see the transaction go from Pending to Successful in around the same blocktime you set in the genesis.


You can click the Check TX Status button to update the status.

AND if all of these steps worked then you've now been successful!!

  
  [ameera](https://www.google.com)
