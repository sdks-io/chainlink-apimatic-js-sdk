
# Off Ramp

*This model accepts additional fields of type unknown.*

## Structure

`OffRamp`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `address` | `string` | Required | OffRamp contract address |
| `version` | `string` | Required | Normalized semantic version of the OffRamp contract<br><br>**Constraints**: *Pattern*: `^\d+\.\d+\.\d+$` |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { OffRamp } from 'chainlink-apimatic-sdk';

const offRamp: OffRamp = {
  address: 'address2',
  version: 'version2',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

