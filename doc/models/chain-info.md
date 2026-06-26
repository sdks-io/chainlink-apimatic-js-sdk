
# Chain Info

Chain information used in lane endpoints. Note: chainType and chainFamily are intentionally excluded from this schema for API responses.

*This model accepts additional fields of type unknown.*

## Structure

`ChainInfo`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `chainId` | [`ChainInfoChainId`](../../doc/models/containers/chain-info-chain-id.md) | Required | This is a container for one-of cases. |
| `displayName` | `string` | Required | Human-readable name of the chain |
| `selector` | `string` | Required | CCIP chain selector as a string |
| `internalId` | `string` | Required | Internal identifier used in configuration |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { ChainInfo } from 'chainlink-apimatic-sdk';

const chainInfo: ChainInfo = {
  chainId: 210,
  displayName: 'displayName0',
  selector: 'selector4',
  internalId: 'internalId6',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

