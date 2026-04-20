# GET /api/v1/agent/swap/status

Check the status of a swap.

```bash
curl 'https://api.ai-dex.io/api/v1/agent/swap/status?hashes=0xApproveHash,0xSwapHash'
```

```json
{
  "status": "completed",
  "steps": [
    {
      "type": "approve",
      "status": "confirmed",
      "transactionHash": "0x...",
      "nonce": 41
    },
    {
      "type": "swap",
      "status": "confirmed",
      "transactionHash": "0x...",
      "nonce": 42,
      "amountIn": "0.5",
      "tokenIn": "ETH",
      "amountOut": "1562.75",
      "tokenOut": "USDC"
    }
  ]
}
```
