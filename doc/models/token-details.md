
# Token Details

*This model accepts additional fields of type unknown.*

## Structure

`TokenDetails`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `symbol` | `string` | Required | Token symbol identifier |
| `lanes` | `Record<string, unknown>` | Required | Available token lanes: source chain to array of destination chains |
| `chains` | [`TokenChainInfo[]`](../../doc/models/token-chain-info.md) | Required | Detailed information about the token on each chain |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { PoolType, TokenDetails } from 'chainlink-apimatic-sdk';

const tokenDetails: TokenDetails = {
  symbol: 'symbol6',
  lanes: {
    'key0': { 'key1': 'val1', 'key2': 'val2' },
    'key1': { 'key1': 'val1', 'key2': 'val2' }
  },
  chains: [
    {
      chainId: 246,
      chainName: 'chainName0',
      tokenAddress: 'tokenAddress0',
      decimals: 18,
      poolType: PoolType.LockRelease,
      poolAddress: 'poolAddress8',
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

