
# Lane Metadata

*This model accepts additional fields of type unknown.*

## Structure

`LaneMetadata`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `environment` | [`MEnvironment`](../../doc/models/m-environment.md) | Required | The network environment |
| `timestamp` | `string` | Required | ISO timestamp of the response |
| `requestId` | `string` | Required | Unique identifier for the request |
| `ignoredLaneCount` | `number` | Required | Number of lanes ignored due to configuration issues<br><br>**Constraints**: `>= 0` |
| `validLaneCount` | `number` | Required | Number of valid lanes in the response<br><br>**Constraints**: `>= 0` |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { LaneMetadata, MEnvironment } from 'chainlink-apimatic-sdk';

const laneMetadata: LaneMetadata = {
  environment: MEnvironment.Mainnet,
  timestamp: '2016-03-13T12:52:32.123Z',
  requestId: '00001fec-0000-0000-0000-000000000000',
  ignoredLaneCount: 98,
  validLaneCount: 68,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

