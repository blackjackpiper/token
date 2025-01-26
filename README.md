## DSurv
A web-application inspired by Curv Finance, a decentralized exchange (DEX) that
focuses on stablecoin trading  
-Gives a new user 10,000 NAND tokens for free to their wallet.
-Option to check the current balance of a user’s wallet using their principal id.
-Can transfer tokens from one user’s wallet to another using principal ids.
-Persistent across refreshes
# To Deploy

1. Find out your principal id:

```
dfx identity get-principal
```

2. Replace the <REPLACE WITH YOUR PRINCIPAL> in main.mo with the principal you got from step 1.

```
  let owner : Principal = Principal.fromText("v4oj7-jd4lf-2rga4-rsx6m-uucev-w4ld4-s2vph-yglan-forox-vnxri-xqe");
```

3. Open up a new terminal in this VSCode project and deploy the token canister:

```
dfx deploy
```

4. Start the frontend:

```
npm start
```

5. Set the canister id to a local variable:

```
CANISTER_PUBLIC_KEY="principal \"$( \dfx canister id token )\""
```

6. Transfer half a billion tokens to the canister Principal ID:

```
dfx canister call token transfer "($CANISTER_PUBLIC_KEY, 500_000_000)"
```

7. Claim the tokens from the faucet on the frontend website.

8. Get token canister id:

```
dfx canister id token
```
