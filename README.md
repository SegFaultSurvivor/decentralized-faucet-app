# 🚰 Decentralized Faucet App with Initium Token 💰  

## Demo  

### 📸 Project Screenshot  
<img width="1280" alt="Screenshot" src="https://github.com/yourusername/initium-faucet/blob/main/public/images/homepage.png">  
<img width="1280" alt="Screenshot" src="https://github.com/yourusername/initium-faucet/blob/main/public/images/claim-tokens.png">  
<img width="1280" alt="Screenshot" src="https://github.com/yourusername/initium-faucet/blob/main/public/images/transaction-history.png">  

### 🎥 Watch the Demo Video  
[Initium Faucet Walkthrough Video](https://github.com/yourusername/initium-faucet/blob/main/public/demo/faucet-demo.mp4)  

---  

## Highlights  

- 🌟 **Tech Stack**: React, Motoko, Internet Computer (ICP)  
- 🔥 **Initium Token (Custom Cryptocurrency)** – Built on ICP blockchain  
- 💸 **Decentralized Faucet** – Claim free Initium Tokens  
- 📜 **Smart Contracts in Motoko** – Secure and transparent transactions  
- 📊 **Real-time Balance Updates** – View token balance instantly  

---  

# Check your Balance

1. Find out your principal id:

```
dfx identity get-principal
```

2. Save it somewhere.

e.g. My principal id is: v2k3j-kogo6-ze7h3-iilgs-crj4m-yobor-5n7xt-fis3b-awvqr-3kx2u-hqe


3. Format and store it in a command line variable:
```
OWNER_PUBLIC_KEY="principal \"$( \dfx identity get-principal )\""
```

4. Check that step 3 worked by printing it out:
```
echo $OWNER_PUBLIC_KEY
```

5. Check the owner's balance:
```
dfx canister call token_backend balanceOf "( $OWNER_PUBLIC_KEY )"
```

# Charge the Canister


1. Check canister ID:
```
dfx canister id token_backend
```

2. Save canister ID into a command line variable:
```
CANISTER_PUBLIC_KEY="principal \"$( \dfx canister id token_backend )\""
```

3. Check canister ID has been successfully saved:
```
echo $CANISTER_PUBLIC_KEY
```

4. Transfer half a billion tokens to the canister Principal ID:
```
dfx canister call token_backend transfer "($CANISTER_PUBLIC_KEY, 500_000_000)"
```

# Deploy the Project to the Live IC Network

1. Create and deploy canisters:

```
dfx deploy --network ic
```

2. Check the live canister ID:
```
dfx canister --network ic id token
```

3. Save the live canister ID to a command line variable:
```
LIVE_CANISTER_KEY="principal \"$( \dfx canister --network ic id token )\""
```

4. Check that it worked:
```
echo $LIVE_CANISTER_KEY
```

5. Transfer some tokens to the live canister:
```
dfx canister --network ic call token_backend transfer "($LIVE_CANISTER_KEY, 50_000_000)"
```

6. Get live canister front-end id:
```
dfx canister --network ic id token_assets
```
7. Copy the id from step 6 and add .raw.ic0.app to the end to form a URL.
e.g. zdv65-7qaaa-aaaai-qibdq-cai.raw.ic0.app
