
# Lane Api Response

*This model accepts additional fields of type unknown.*

## Structure

`LaneApiResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `metadata` | [`LaneMetadata`](../../doc/models/lane-metadata.md) | Required | - |
| `data` | [`Record<string, LaneDetails>`](../../doc/models/lane-details.md) | Required | Lane data organized by dynamic lane keys (e.g., '1_to_56', 'ethereum-mainnet_to_polygon-mainnet') |
| `ignored` | [`LaneConfigError[]`](../../doc/models/lane-config-error.md) | Required | List of lanes that could not be configured |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { LaneApiResponse, MEnvironment } from 'chainlink-apimatic-sdk';

const laneApiResponse: LaneApiResponse = {
  metadata: {
    environment: MEnvironment.Mainnet,
    timestamp: '2016-03-13T12:52:32.123Z',
    requestId: '000009f4-0000-0000-0000-000000000000',
    ignoredLaneCount: 186,
    validLaneCount: 156,
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  data: {
    'key0': {
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
        'supportedTokens1',
        'supportedTokens0'
      ],
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    'key1': {
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
        'supportedTokens1',
        'supportedTokens0'
      ],
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    'key2': {
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
        'supportedTokens1',
        'supportedTokens0'
      ],
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  },
  ignored: [
    {
      sourceChain: 'sourceChain4',
      destinationChain: 'destinationChain4',
      reason: 'reason6',
      missingFields: [
        'missingFields9',
        'missingFields0'
      ],
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

