
# On Ramp

*This model accepts additional fields of type unknown.*

## Structure

`OnRamp`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `address` | `string` | Required | OnRamp contract address |
| `version` | `string` | Required | Normalized semantic version of the OnRamp contract<br><br>**Constraints**: *Pattern*: `^\d+\.\d+\.\d+$` |
| `enforceOutOfOrder` | `boolean \| undefined` | Optional | Whether the OnRamp enforces out-of-order execution |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { OnRamp } from 'chainlink-apimatic-sdk';

const onRamp: OnRamp = {
  address: 'address0',
  version: 'version0',
  enforceOutOfOrder: false,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

