# GET /api/v1/agent/tokens

Find a token by symbol or address.

```bash
curl 'https://api.ai-dex.io/api/v1/agent/tokens?term=USDC'
```

```json
[
  {
    "address": "0xA0b86991c6218b36c1d19D4a2e9Eb0cE3606eB48",
    "symbol": "USDC",
    "decimals": 6,
    "name": "USD Coin",
    "imageUrl": "https://..."
  }
]
```
