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

going back to your MyCrypto wallet
  
  [ameera](https://www.google.com)
