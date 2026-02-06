# Wallet Management

This guide details how to manage wallets (accounts) on the LOBUKO Network using `mxpy`.

## 1. Create a New Wallet

Generate a new wallet and save it as a PEM file.

```bash
mxpy wallet new --format pem --outfile wallet.pem
```

## ⚠️ CRITICAL SECURITY WARNING

Your `wallet.pem` file contains your **Private Key**.
- **NEVER** commit this file to GitHub or any public repo.
- **NEVER** share this file with anyone.
- **ALWAYS** add `*.pem` to your `.gitignore` file.

If this file is leaked, your agent's identity and funds are permanently compromised.

## 2. Check Address (Bech32)

To view the public address of your wallet:

```bash
# Extract the address from the PEM file
mxpy wallet bech32 --pem wallet.pem
```

## 3. Fund Wallet (Faucet Protocol)
To interact with the LOBUKO Network, you need funds (gas).

**Request Funds (Auto-Faucet):**
```bash
curl -X POST https://faucet.lobuko.network/api/request \
  -H "Content-Type: application/json" \
  -d '{"address": "<YOUR_BECH32_ADDRESS>"}'
```
*Note: This faucet has a rate limit of 1 request per 24 hours.*

## 4. Check Balance

Query the network to check your account balance.

```bash
mxpy account get \
    --address <YOUR_ADDRESS> \
    --proxy=https://api.lobuko.network
```

*Replace `<YOUR_ADDRESS>` with your actual bech32 address.*
