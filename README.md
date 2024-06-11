# Pump Fun Token Project

## Overview

This guide provides step-by-step instructions for setting up, building, deploying, and testing the Pump Fun Token project using Anchor and Solana. The guide also covers how to interact with the deployed smart contract using a client script and setting up the frontend.

## Prerequisites

1. Install Anchor

sh cargo install --git https://github.com/project-serum/anchor anchor-cli --locked

2. Install Node.js and NPM

   curl -fsSL https://deb.nodesource.com/setup_16.x | sudo -E bash -
   sudo apt-get install -y nodejs
   

Step 1: Set Up Environment Variables

Set the environment variables for Anchor:

export ANCHOR_WALLET=/Users/user/.config/solana/id.json
export ANCHOR_PROVIDER_URL=http://127.0.0.1:8899


Step 2: Run Solana Test Validator

Open a terminal window and start the Solana test validator:

solana-test-validator

Step 3: Build the Project

Open another terminal window and navigate to the project directory:

cd /Users/user/Desktop/pump_fun_token


Add the `idl-build` feature to the `Cargo.toml` file in the `programs/pump_fun_token` directory:

[features]
idl-build = ["anchor-lang/idl-build", "anchor-spl/idl-build"]


Build the project:

anchor build


 Step 4: Deploy the Project

Deploy the smart contract to the local test validator:

anchor deploy


Step 5: Install Project Dependencies

Navigate to the root directory and install the necessary NPM packages:

npm install @project-serum/anchor


Step 6: Run the Client Script

Run your client script to interact with the deployed smart contract:

node client.js


Client Script (client.js)

The `client.js` file in the root directory is used to interact with the deployed smart contract. This script can be used to perform actions such as buying and selling tokens on the Solana blockchain.

Step 7: Setting Up the Frontend

Navigate to the frontend directory and install the dependencies:

cd frontend
npm install

Troubleshooting

- If you encounter an error regarding the `ANCHOR_WALLET` environment variable, ensure it is set correctly in your terminal.
- Ensure that the Solana test validator is running before deploying the project.
- Check the `Cargo.toml` file for any syntax errors or missing 

To check the token accounts
 
solana account <user_token_account_public_key>
solana account <pool_token_account_public_key>
