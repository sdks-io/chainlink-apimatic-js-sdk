
# Lane Config Error

*This model accepts additional fields of type unknown.*

## Structure

`LaneConfigError`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `sourceChain` | `string` | Required | Source chain identifier that failed configuration |
| `destinationChain` | `string` | Required | Destination chain identifier that failed configuration |
| `reason` | `string` | Required | Human-readable reason for the configuration failure |
| `missingFields` | `string[]` | Required | List of missing or invalid configuration fields |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { LaneConfigError } from 'chainlink-apimatic-sdk';

const laneConfigError: LaneConfigError = {
  sourceChain: 'sourceChain8',
  destinationChain: 'destinationChain8',
  reason: 'reason2',
  missingFields: [
    'missingFields3',
    'missingFields4',
    'missingFields5'
  ],
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

