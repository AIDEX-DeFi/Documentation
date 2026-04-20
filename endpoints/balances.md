# GET /api/v1/agent/balances

Get token balances and router allowances for a wallet.

```bash
curl 'https://api.ai-dex.io/api/v1/agent/balances?address=0xYourWallet&tokens=ETH,USDC'
```

```json
[
  {
    "address": "0x0000000000000000000000000000000000000000",
    "symbol": "ETH",
    "balance": "1.5",
    "allowance": null
  },
  {
    "address": "0xA0b86991c6218b36c1d19D4a2e9Eb0cE3606eB48",
    "symbol": "USDC",
    "balance": "3250.00",
    "allowance": "1000.0"
  }
]
```
