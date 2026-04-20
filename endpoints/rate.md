# POST /api/v1/agent/rate

Quote an exchange rate.

```bash
curl -X POST 'https://api.ai-dex.io/api/v1/agent/rate' \
  -H 'Content-Type: application/json' \
  -d '{
    "tokenIn": "ETH",
    "tokenOut": "USDC",
    "amountIn": "0.5"
  }'
```

```json
{
  "rate": "3125.50",
  "amountOut": "1562.75",
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
