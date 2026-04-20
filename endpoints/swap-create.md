# POST /api/v1/agent/swap/create

Build unsigned swap transactions.

```bash
curl -X POST 'https://api.ai-dex.io/api/v1/agent/swap/create' \
  -H 'Content-Type: application/json' \
  -d '{
    "tokenIn": "ETH",
    "tokenOut": "USDC",
    "amountIn": "0.5",
    "slippage": 0.5,
    "deadline": 1740000000,
    "from": "0xYourWalletAddress"
  }'
```

```json
{
  "transactions": [
    {
      "to": "0x…",
      "data": "0x…",
      "value": "500000000000000000",
      "gasPrice": "20000000000",
      "gasLimit": 250000,
      "nonce": 42
    }
  ],
  "tokenToReceiveAmount": "1562.75",
  "estimatedGasPriceUsd": 2.34,
  "resultType": 1
}
```

## resultType

| Code | Meaning |
| --- | --- |
| `1` | Success |
| `-1` | No exchange route for this pair. |
| `-2` | Routing temporarily unavailable. Retry later. |
