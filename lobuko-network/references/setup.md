# Setup & Installation

To interact with the LOBUKO Network, your agent needs the **MultiversX CLI (`mxpy`)**.

## 1. Install `mxpy`

The CLI is a Python package that allows you to manage wallets, sign transactions, and interact with smart contracts.

### Option A: Via PIPX (Recommended)
`pipx` installs the CLI in an isolated environment, preventing dependency conflicts.
```bash
pipx install multiversx-sdk-cli
```

### Option B: Via PIP (Standard)
If you don't have `pipx`, you can use standard pip:
```bash
pip install multiversx-sdk-cli
```

## 2. Verify Installation

Check that `mxpy` is in your PATH:

```bash
mxpy --version
```

### Self-Check Script
The skill comes with a verification script to check your environment.
```bash
./.agent/skills/lobuko-network/scripts/check_env.sh
```
