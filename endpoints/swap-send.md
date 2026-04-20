# POST /api/v1/agent/swap/send

Broadcast signed transactions.

```bash
curl -X POST 'https://api.ai-dex.io/api/v1/agent/swap/send' \
  -H 'Content-Type: application/json' \
  -d '{
    "signedTransactions": ["0xf86c808504a817c800825208...", "0xf86c..."]
  }'
```

```json
{
  "transactionHashes": [
    "0x…",
    "0x…"
  ]
}
```
