# PPT Invoicing Suite

## Overview

The **PPT Invoicing Suite** is a decentralized invoicing and file storage system powered by the Park Pro Token (PPT), an ERC-20 token deployed on the Filecoin Virtual Machine (FVM). This project integrates secure file storage using Storacha, token-gated access using smart contracts, and a full-stack invoicing dApp architecture.

This repository serves as a monorepo containing the following interconnected submodules:

---

## Submodules

### 1. [`Invoice-storage-storacha`](https://github.com/virtualvasu/Invoice-storage-storacha.git)

A React-based frontend dApp that allows users to securely upload and store invoice files using **Storacha**, built on Web3.Storage. Files are encrypted and uploaded to IPFS, and their CIDs are returned for access or sharing.

**Features:**

* Secure, client-side file encryption
* Decentralized file upload via Web3.Storage
* DID-based user authentication

**Path:** `Invoice-storage-storacha`

---

### 2. [`PPT-token-filecoin`](https://github.com/virtualvasu/PPT-token-filecoin.git)

This module contains the smart contract for the **Park Pro Token (PPT)**, an ERC-20 token deployed on FVM-compatible chains like Calibration and Sepolia. It serves as the core token used for gating access to services and managing subscriptions.

**Features:**

* ERC-20 contract written in Solidity
* Deployed on Filecoin Calibration testnet and Ethereum Sepolia testnet
* Supports balance checks and token gating

**Path:** `PPT-token-filecoin`

---

### 3. [`PPTToken-gated-filecoin`](https://github.com/virtualvasu/PPTToken-gated-filecoin.git)

A dApp that uses the Park Pro Token to gate access to invoice generation features. Users must hold a minimum balance of PPT to unlock access, simulating a token-based subscription model.

**Features:**

* Wallet connection via MetaMask
* Network detection and switching
* Token balance verification before granting access

**Path:** `PPTToken-gated-filecoin`

---

## Architecture

```
+---------------------------+
|   ppt-invoicing-suite     |
|  (Super Repo - Monorepo) |
+-----------+---------------+
            |
            | Submodules
            |
    +-------+--------+----------------+
    |                |                |
    v                v                v
Invoice-      PPT-token-       PPTToken-gated-
storage-      filecoin          filecoin
storacha
```

Each module is independently deployable and connected through shared logic via token usage and IPFS CIDs.

---

## Getting Started

To clone and initialize the project with submodules:

```bash
git clone --recurse-submodules https://github.com/virtualvasu/ppt-invoicing-suite
cd ppt-invoicing-suite
```

To update submodules later:

```bash
git submodule update --remote --merge
```

---

## Development Workflow

1. Navigate into any submodule to make code changes.
2. Commit and push changes from within the submodule.
3. Go back to the root (`ppt-invoicing-suite`) and commit the updated submodule reference:

   ```bash
   git add <submodule-name>
   git commit -m "Update submodule"
   git push origin main
   ```


