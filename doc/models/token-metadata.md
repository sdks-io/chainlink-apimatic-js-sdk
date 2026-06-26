
# Token Metadata

*This model accepts additional fields of type unknown.*

## Structure

`TokenMetadata`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `environment` | [`MEnvironment`](../../doc/models/m-environment.md) | Required | The network environment |
| `timestamp` | `string` | Required | ISO timestamp of the response |
| `requestId` | `string` | Required | Unique identifier for the request |
| `ignoredTokenCount` | `number` | Required | Number of tokens ignored due to configuration issues<br><br>**Constraints**: `>= 0` |
| `validTokenCount` | `number` | Required | Number of valid tokens in the response<br><br>**Constraints**: `>= 0` |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { MEnvironment, TokenMetadata } from 'chainlink-apimatic-sdk';

const tokenMetadata: TokenMetadata = {
  environment: MEnvironment.Mainnet,
  timestamp: '2016-03-13T12:52:32.123Z',
  requestId: '000022de-0000-0000-0000-000000000000',
  ignoredTokenCount: 130,
  validTokenCount: 202,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

