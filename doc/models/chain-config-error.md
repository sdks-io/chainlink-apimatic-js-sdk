
# Chain Config Error

*This model accepts additional fields of type unknown.*

## Structure

`ChainConfigError`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `chainId` | `number` | Required | Chain ID of the failed configuration |
| `networkId` | `string` | Required | Network identifier of the failed configuration |
| `reason` | `string` | Required | Reason for the configuration failure |
| `missingFields` | `string[]` | Required | List of missing required fields |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { ChainConfigError } from 'chainlink-apimatic-sdk';

const chainConfigError: ChainConfigError = {
  chainId: 86,
  networkId: 'networkId4',
  reason: 'reason4',
  missingFields: [
    'missingFields1',
    'missingFields2'
  ],
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

