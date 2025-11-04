# 💎 Message Storing DApp  

A simple **Decentralized Application (DApp)** built using **Ethereum, MetaMask, and Remix** that allows users to **store and retrieve messages** directly on the blockchain.  

This project demonstrates how to integrate a **Solidity Smart Contract** with a **frontend webpage** using **ethers.js** and the **MetaMask browser wallet**.  

---

## 🚀 Features

✅ Connects to **MetaMask** wallet (Injected Provider)  
✅ Lets users **store messages** on the blockchain  
✅ Retrieves and displays **all previously stored messages**  
✅ Built using **Remix IDE** for Smart Contract deployment  
✅ Clean, modern, and responsive **frontend (HTML + CSS)**  

---

## 🧱 Project Structure

---
message-storing-dapp/
│
├── index.html # Main frontend UI
├── style.css # Styling for DApp
├── MessageDapp.sol # Solidity Smart Contract
└── README.md # Documentation (this file)

## ⚙️ Smart Contract (Solidity)

The DApp uses the following **Solidity contract**.  
If you want to redeploy it yourself, you can do so using **Remix IDE** and **MetaMask**.


// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract MessageDapp {
    string[] public messages;

  // Store a new message
    function setMessage(string memory _message) public {
        messages.push(_message);
    }

  // Read all messages
    function getAllMessages() public view returns (string[] memory) {
        return messages;
    }

  // Get only the latest message
    function getLatestMessage() public view returns (string memory) {
        if (messages.length == 0) return "";
        return messages[messages.length - 1];
    }
}


🧩 Frontend Overview

index.html → Connects MetaMask and interacts with the contract using ethers.js

style.css → Adds a professional and modern UI design

No external backend — it’s fully decentralized

The main interactions are:

setMessage() → Write new message to blockchain

getAllMessages() → Retrieve all messages

🧰 Requirements

To run or modify this project, you’ll need:

Tool	Purpose	Link
MetaMask	Wallet and blockchain connector	https://metamask.io

Remix IDE	Deploying Solidity contracts	https://remix.ethereum.org

Ethereum Testnet	(Optional) For real blockchain simulation	Sepolia Testnet

VS Code or Any Editor	To edit the files	https://code.visualstudio.com
🪜 Step-by-Step Setup Guide
🧱 Step 1 — Deploy Smart Contract on Remix

Open Remix IDE

Create a new file → MessageDapp.sol

Paste the contract code above

Compile the contract using compiler version 0.8.x

Go to Deploy & Run Transactions tab

Environment: Injected Provider – MetaMask

Click Deploy

MetaMask will ask for confirmation → approve it

Copy the Deployed Contract Address (you’ll need this for frontend)

💻 Step 2 — Connect Frontend to Contract

Open your index.html file in VS Code

Find this line:

const contractAddress = "PASTE-YOUR-CONTRACT-ADDRESS-HERE";


Replace it with the address you copied from Remix

Save the file

🌐 Step 3 — Run the Frontend

You can run it locally in two ways:

Option 1: Using VS Code Live Server

Right-click index.html

Click “Open with Live Server”

Option 2: Open directly

Double-click index.html

Allow MetaMask to connect when prompted

✍️ Step 4 — Use the DApp

Enter a message and click “Set Message (write)”

Wait for MetaMask to confirm the transaction

Click “Get Message (read)” to see all messages

🧠 How It Works

Each user interacts with the same deployed contract

Messages are stored on-chain in an array

The frontend reads them via the ethers.js library

Every transaction is signed by MetaMask for security

🧩 Example Output

Stored Messages:

Hello | Blockchain | Crypto | Ethereum Rocks 🚀


Network Status:

Connected: 0x0918... ✅
🧑‍💻 Developer Info

Project by:
👤 U K Rohit Krishna
📚 MSc Cybersecurity Student
🧠 Focus: Blockchain, Networking, Cybersecurity

📜 License

This project is open source and available under the MIT License
.


