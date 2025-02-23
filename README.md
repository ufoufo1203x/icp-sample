# How to deploy ICP Sample Canister

## 🌍 What is ICP?
The **Internet Computer Protocol (ICP)** is a blockchain network that enables smart contract execution at web speed, allowing developers to build decentralized applications (DApps) that run directly on the blockchain without centralized cloud providers. It is designed to provide a scalable, secure, and efficient ecosystem for running Web3 applications.

## 🏗 What is a Canister?
A **Canister** is a computational unit on the ICP network, similar to a smart contract on other blockchains but with additional capabilities. Canisters contain both the backend (WebAssembly modules, often written in Rust or Motoko) and frontend assets, allowing them to serve web applications directly. They execute logic, store data, and interact with other canisters and users in a decentralized manner.

## 🔄 What are Cycles?
**Cycles** are the computational resource used to power canisters on the Internet Computer. They function similarly to gas fees on Ethereum but are designed for predictable and stable pricing. Cycles are used to pay for computation, storage, and message execution within the ICP ecosystem.

- **Conversion:** ICP tokens can be converted into cycles.
- **Usage:** Every action a canister performs, such as executing functions, storing data, or communicating with other canisters, consumes cycles.
- **Refilling:** Developers need to replenish cycles periodically to keep their canisters running.

Without sufficient cycles, a canister will stop executing. This ensures efficient resource management across the network.

## 🎯 Project Purpose
This project is a simple smart contract deployed on the Internet Computer Protocol (ICP). It demonstrates how to create and interact with a basic canister. It uses Rust to implement a `greet` function that returns "Hello, [name]!" when a name is provided. 

The frontend provides a simple web interface, allowing users to call the `greet` function directly.

## 🔧 Deployment Guide
Follow these steps to deploy the project locally or on the ICP mainnet.

### 1️⃣ Install ICP SDK
First, set up the ICP development environment:
```sh
sh -ci "$(curl -fsSL https://internetcomputer.org/install.sh)"
```

### 2️⃣ Clone the Repository
```sh
git clone https://github.com/Krminfinity/icp-sample.git
cd icp-sample
```

### 3️⃣ Deploy Locally
Run the following commands to deploy the canister locally:
```sh
dfx start --background
dfx deploy
```

### 4️⃣ Deploy to ICP Mainnet (Optional)
To deploy on the ICP network, run:
```sh
dfx deploy --network ic
```
**Note:** Deploying to the mainnet requires **Cycles (fees).** Ensure your canister has enough cycles to function properly.

## 🔍 Testing the Deployment
After deployment, verify the smart contract functionality.

### ✅ 1. Test the Frontend
Open the following URL in your browser:
```
http://bd3sg-teaaa-aaaaa-qaaba-cai.localhost:4943/
```
Ensure the DApp loads and users can call the `greet` function.

### ✅ 2. Test the Backend (Smart Contract)
Open Candid UI and execute the `greet` function:
```
http://127.0.0.1:4943/?canisterId=bkyz2-fmaaa-aaaaa-qaaaq-cai
```
Or call the function via the terminal:
```sh
dfx canister call hello_backend greet "Your name"
```
Expected Output:
```
("Hello, Your name!")
```

---

Enjoy ICP and coding🚀

