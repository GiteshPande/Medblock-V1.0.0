# Medblock-V1.0.0 - Blockchain for Health Data Management

## Introduction

The aims of this application are:-
- To implement blockchain technology for storing, updating, and retriving EHR.
- To provide secure storage of electronic records by defining granular access rules for the users of the proposed application. 
- This application also discusses the scalability problem faced by the blockchain technology in general via use of off-chain storage of the records. This application provides the EHR system with the benefits of having a scalable, secure and integral blockchain-based solution.

### Video Demo: [Link](https://drive.google.com/drive/folders/1L_RbuDFJvPhj8KgBxLrdmfUuBdAR5SWD?usp=sharing)


## Installation Procdure

This application requires NodeJS, npm, Truffle, Ganache, and IPFS to work. Instruction to install all, and setup dependencies are given below.

## Node Modules

1. Move to the project directory `cd app`
2. Run `npm install` to install project dependencies.

## Ganache

1. Go to [Ganache homepage](https://truffleframework.com/ganache) and download.
2. If you are on Linux, you must have received an `.appimage` file. Follow installation instructions available [here](https://itsfoss.com/use-appimage-linux/).

## IPFS (Inter Planatery File System)

1. Go to the [github page](https://github.com/ipfs/ipfs-desktop) of IPFS and install IPFS Desktop.

## Local Server

1. Install Node lite-server by running the following command on your terminal from project root directory `npm install -g lite-server`.

## Metamask

1. Metamask is a browser extension available for Google Chrome, Mozilla Firefox and Brave Browser.
2. Add Metamask to your browser by clicking [here](http://metamask.io/).

## Getting the DApp running

### 1. Ganache
* Open Ganache and create a new Workspace.
* Add [truffle_config.js](https://github.com/GiteshPande/Medblock-V1.0.0/blob/main/app/truffle-config.js) in `Add Project Section`
* Under **Server** tab:
  - Set Hostname to `127.0.0.1 -lo`.
  - Set Port Number to `8545`.
  - Enable Automine.
* Under **Accounts & Keys** tab:
  - Enable Autogenerate HD Mnemonic

### 2. IPFS
* Fire up your terminal and run `ipfs init`. If it says command not found then follow this [link](https://docs.ipfs.tech/install/command-line/#linux)
* Then type the following command from your project root directory.
```bash
ipfs config --json API.HTTPHeaders.Access-Control-Allow-Origin "['*']"
ipfs config --json API.HTTPHeaders.Access-Control-Allow-Credentials "['true']"
ipfs config --json API.HTTPHeaders.Access-Control-Allow-Methods "['PUT', 'POST', 'GET']"
```
**Note** - If you face any issues with the above command on windows, try using command prompt and escape sequences or git bash, same goes for Linux, Mac and other machines.

### 3. Metamask
- After installing Metamask, click on the metamask icon on your browser.
- Click on continue and accept all the terms and conditions after reading them.
- Stop when Metamask asks you to create a new password. We will come back to this after deploying the contract in the next section.

### 4. Smart Contract
- Install Truffle using `npm install truffle -g`.
- Compile Contracts using `truffle compile`.

  #### 1. Starting your local development blockchain
    - Open Ganache.
    - Make sure to configure it the way mentioned above.
    - Open new Terminal and deploy contracts using `truffle migrate`.
    - Open [Remix](https://remix.ethereum.org/), upload `MedBloack.sol` and then deploy it.
    - Copy deployed contract address to src/js/app.js
    ```js
    // app/src/app.js  line number 11
    var agentContractAddress = '0x75E115394aacC7c6063E593B9292CB9417E4cbeC';
    ```
    - If you change contents of any contract , replace existing deployment using `truffle migrate --reset`.
    - Deploy the modified contract on remix and change the ABI in src/js/app/js to the `deploted contract` ABI.

### 5. Running the DApp.
  #### 1. Connecting Metamask to our local blockchain
    - Connect metamask to localhost:8485
    - Click on `Import Account`.
    - Select any account from ganache and copy the private key to import account into metaMask.
    
  #### 2. Starting IPFS
    - Start the IPFS Desktop Application
    
  #### 3. Starting Local Server
    - Open a new terminal window and navigate to `/YOUR_PROJECT_DIRECTORY/app/`.
    - Run `npm start`.
    - Open `localhost:3000` on your browser.

### Eureka! Eureka ! The DApp is up and running locally

## Contribution

We have added a new `FurtherImprovement.md` file please go ahead, read it, review it and drop your suggestions as a PR :smiley:.
