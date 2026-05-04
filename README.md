# Blockchain Student Election System

A decentralized student election platform built on Ethereum 
using Solidity smart contracts and a Web3.js frontend.

## Overview
Traditional student elections are vulnerable to tampering 
and lack transparency. This system solves that by recording 
votes immutably on-chain — making results transparent, 
tamper-proof, and verifiable by anyone.

## Tech Stack
- **Smart Contracts:** Solidity
- **Frontend:** HTML, CSS, Vanilla JavaScript
- **Blockchain Interaction:** Web3.js
- **Network:** Ethereum (tested on Sepolia testnet)

## Features
- Immutable on-chain vote recording
- One wallet = one vote enforcement
- Real-time vote count visibility
- Transparent election results anyone can verify
- Successfully tested at high school level in Indonesia

## How It Works
1. Admin deploys the election contract with candidate list
2. Eligible voters connect their MetaMask wallet
3. Each voter casts exactly one vote — enforced by smart contract
4. Results are visible in real time on-chain
5. No central authority can alter results after deployment

## What I Learned
- Writing and deploying Solidity smart contracts
- Preventing double-voting using mapping data structures
- Connecting a frontend to Ethereum using Web3.js
- Understanding how immutability creates trust in governance

## Smart Contract Logic
The core contract prevents double voting using a mapping:
\`\`\`solidity
mapping(address => bool) public hasVoted;

function vote(uint candidateId) public {
    require(!hasVoted[msg.sender], "Already voted");
    hasVoted[msg.sender] = true;
    candidates[candidateId].voteCount++;
}
\`\`\`

## Future Improvements
- ZK proof integration for anonymous but verifiable voting
- Multi-election support
- Mobile-responsive frontend
- Formal security audit
