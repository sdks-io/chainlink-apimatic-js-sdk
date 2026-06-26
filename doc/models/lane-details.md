
# Lane Details

*This model accepts additional fields of type unknown.*

## Structure

`LaneDetails`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `sourceChain` | [`ChainInfo`](../../doc/models/chain-info.md) | Required | Chain information used in lane endpoints. Note: chainType and chainFamily are intentionally excluded from this schema for API responses. |
| `destinationChain` | [`ChainInfo`](../../doc/models/chain-info.md) | Required | Chain information used in lane endpoints. Note: chainType and chainFamily are intentionally excluded from this schema for API responses. |
| `onRamp` | [`OnRamp`](../../doc/models/on-ramp.md) | Required | - |
| `offRamp` | [`OffRamp`](../../doc/models/off-ramp.md) | Required | - |
| `supportedTokens` | `string[]` | Required | List of supported token keys (e.g., LINK, CCIP-BnM, USDC) |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { LaneDetails } from 'chainlink-apimatic-sdk';

const laneDetails: LaneDetails = {
  sourceChain: {
    chainId: 214,
    displayName: 'displayName6',
    selector: 'selector8',
    internalId: 'internalId0',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  destinationChain: {
    chainId: 250,
    displayName: 'displayName6',
    selector: 'selector8',
    internalId: 'internalId0',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  onRamp: {
    address: 'address0',
    version: 'version0',
    enforceOutOfOrder: false,
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  offRamp: {
    address: 'address2',
    version: 'version2',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  supportedTokens: [
    'supportedTokens7'
  ],
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

