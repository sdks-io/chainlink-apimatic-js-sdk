
# Token Api Response

*This model accepts additional fields of type unknown.*

## Structure

`TokenApiResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `metadata` | [`TokenMetadata`](../../doc/models/token-metadata.md) | Required | - |
| `data` | [`Record<string, TokenChainData>`](../../doc/models/token-chain-data.md) | Required | Token data indexed by token symbol and then by chain ID/selector |
| `ignored` | [`TokenConfigError[]`](../../doc/models/token-config-error.md) | Required | List of tokens that were ignored due to configuration issues |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import {
  MEnvironment,
  PoolType,
  TokenApiResponse,
} from 'chainlink-apimatic-sdk';

const tokenApiResponse: TokenApiResponse = {
  metadata: {
    environment: MEnvironment.Mainnet,
    timestamp: '2016-03-13T12:52:32.123Z',
    requestId: '000009f4-0000-0000-0000-000000000000',
    ignoredTokenCount: 212,
    validTokenCount: 32,
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  data: {
    'key0': {
      chainId: 242,
      chainName: 'chainName4',
      tokenAddress: 'tokenAddress4',
      decimals: 16,
      poolType: PoolType.LockRelease,
      poolAddress: 'poolAddress2',
      name: 'name0',
      symbol: 'symbol2',
      destinations: [
        'destinations8'
      ],
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    'key1': {
      chainId: 242,
      chainName: 'chainName4',
      tokenAddress: 'tokenAddress4',
      decimals: 16,
      poolType: PoolType.LockRelease,
      poolAddress: 'poolAddress2',
      name: 'name0',
      symbol: 'symbol2',
      destinations: [
        'destinations8'
      ],
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  },
  ignored: [
    {
      symbol: 'symbol0',
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

