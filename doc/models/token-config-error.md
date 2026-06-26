
# Token Config Error

*This model accepts additional fields of type unknown.*

## Structure

`TokenConfigError`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `symbol` | `string` | Required | Token symbol |
| `reason` | `string` | Required | Reason for the configuration error |
| `missingFields` | `string[]` | Required | List of missing required fields |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { TokenConfigError } from 'chainlink-apimatic-sdk';

const tokenConfigError: TokenConfigError = {
  symbol: 'symbol0',
  reason: 'reason6',
  missingFields: [
    'missingFields9',
    'missingFields0'
  ],
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

