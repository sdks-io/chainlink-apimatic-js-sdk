
# Token Chain Info

*This model accepts additional fields of type unknown.*

## Structure

`TokenChainInfo`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `chainId` | [`TokenChainInfoChainId`](../../doc/models/containers/token-chain-info-chain-id.md) | Required | This is a container for one-of cases. |
| `chainName` | `string` | Required | Human-readable name of the chain |
| `tokenAddress` | `string` | Required | Token contract address on this chain |
| `decimals` | `number` | Required | Number of decimals used for the token<br><br>**Constraints**: `>= 0`, `<= 18` |
| `poolType` | [`PoolType`](../../doc/models/pool-type.md) | Required | Type of pool for this token |
| `poolAddress` | `string` | Required | Token pool contract address (if applicable) |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { PoolType, TokenChainInfo } from 'chainlink-apimatic-sdk';

const tokenChainInfo: TokenChainInfo = {
  chainId: 112,
  chainName: 'chainName8',
  tokenAddress: 'tokenAddress2',
  decimals: 18,
  poolType: PoolType.Usdc,
  poolAddress: 'poolAddress6',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

