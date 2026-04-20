# AIDEX Agents API

Lightning-fast DEX aggregator for swapping tokens on-chain.

The AIDEX Agents API is a public HTTP interface covering the full swap lifecycle: token search, exchange rates, wallet balances, and a build-sign-broadcast flow with client-side signing.

## Base URL

```
https://api.ai-dex.io
```

## Authorization

The AIDEX Agents API is public. No API key or authentication is required.

## Specifications and Playground

- [Interactive playground](https://api.ai-dex.io/scalar/agent)
- [OpenAPI 3.1 spec](https://api.ai-dex.io/openapi/agent.json)

## Getting Started

Quote the current ETH → USDC rate for 0.5 ETH:

```bash
curl -X POST 'https://api.ai-dex.io/api/v1/agent/rate' \
  -H 'Content-Type: application/json' \
  -d '{ "tokenIn": "ETH", "tokenOut": "USDC", "amountIn": "0.5" }'
```

```json
{
  "rate": "3125.50",
  "amountOut": "1562.75",
  "estimatedGasPriceUsd": 2.34,
  "resultType": 1
}
```

## Endpoints

| Method | Path | Description |
| --- | --- | --- |
| GET  | [`/api/v1/agent/tokens`](endpoints/tokens.md)             | Find a token by symbol or address. |
| POST | [`/api/v1/agent/rate`](endpoints/rate.md)                 | Quote an exchange rate. |
| GET  | [`/api/v1/agent/balances`](endpoints/balances.md)         | Get token balances and router allowances for a wallet. |
| POST | [`/api/v1/agent/swap/create`](endpoints/swap-create.md)   | Build unsigned swap transactions. |
| POST | [`/api/v1/agent/swap/send`](endpoints/swap-send.md)       | Broadcast signed transactions. |
| GET  | [`/api/v1/agent/swap/status`](endpoints/swap-status.md)   | Check the status of a swap. |

## Supported Networks

| Network          | Chain ID | Status      |
| ---------------- | -------- | ----------- |
| Ethereum Mainnet | 1        | Live        |
| Polygon          | 137      | Coming soon |
| BNB Smart Chain  | 56       | Coming soon |
| Arbitrum One     | 42161    | Coming soon |
| Optimism         | 10       | Coming soon |
| Base             | 8453     | Coming soon |

## Error responses

On failure, every endpoint returns a JSON envelope:

```json
{
  "error": {
    "code": 2,
    "message": "Token not found"
  }
}
```

The `message` is human-readable and safe to surface directly to end users. The numeric `code` classifies the failure so clients can react programmatically:

| Code | Meaning |
| --- | --- |
| `0` | Service temporarily unavailable. Back off and retry. |
| `1` | Unsupported client version. Update your client. |
| `2` | Invalid request. See `message` for details. |

## License

See [LICENSE](LICENSE).
