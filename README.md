# Para Wallet Skill

A [ClawhHub](https://clawhhub.com) Agent Skill that teaches AI agents to create blockchain wallets and sign transactions using [Para's](https://getpara.com) MPC infrastructure.

## What It Does

Gives agents the knowledge to use Para's REST API for:

- **Creating wallets** on EVM and Solana
- **Checking wallet status** (async creation with polling)
- **Signing arbitrary data** via MPC — the private key never exists in one place

## Install

```bash
npm i -g clawdhub && clawdhub install para-wallet
```

Or copy [`SKILL.md`](./SKILL.md) directly into your agent's skills directory.

## Setup

1. Get an API key from [developer.getpara.com](https://developer.getpara.com)
2. Set the environment variable:
   ```
   export PARA_API_KEY="your-secret-api-key"
   ```

## API Endpoints Covered

| Endpoint | Method | Purpose |
|----------|--------|---------|
| `/v1/wallets` | POST | Create a wallet (EVM/Solana) |
| `/v1/wallets/{walletId}` | GET | Get wallet status + address |
| `/v1/wallets/{walletId}/sign-raw` | POST | Sign 0x-hex data via MPC |

## Why Para for Agents

Para uses Multi-Party Computation — the private key is split into shares across independent parties and never assembled. This means agents can sign transactions without ever holding a full key, eliminating the risk of key leakage.

## License

MIT
