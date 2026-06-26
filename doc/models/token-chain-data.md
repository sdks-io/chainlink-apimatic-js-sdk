
# Token Chain Data

*This model accepts additional fields of type unknown.*

## Structure

`TokenChainData`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `chainId` | [`TokenChainDataChainId`](../../doc/models/containers/token-chain-data-chain-id.md) | Required | This is a container for one-of cases. |
| `chainName` | `string` | Required | Human-readable name of the chain |
| `tokenAddress` | `string` | Required | Token contract address on this chain |
| `decimals` | `number` | Required | Number of decimals used for the token<br><br>**Constraints**: `>= 0`, `<= 18` |
| `poolType` | [`PoolType`](../../doc/models/pool-type.md) | Required | Type of pool for this token |
| `poolAddress` | `string` | Required | Token pool contract address (if applicable) |
| `name` | `string \| undefined` | Optional | Name of the token |
| `symbol` | `string \| undefined` | Optional | Symbol of the token |
| `destinations` | `string[] \| undefined` | Optional | Destination chains this token can be sent to |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { PoolType, TokenChainData } from 'chainlink-apimatic-sdk';

const tokenChainData: TokenChainData = {
  chainId: 156,
  chainName: 'chainName6',
  tokenAddress: 'tokenAddress4',
  decimals: 18,
  poolType: PoolType.Usdc,
  poolAddress: 'poolAddress4',
  name: 'name2',
  symbol: 'symbol6',
  destinations: [
    'destinations4'
  ],
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

