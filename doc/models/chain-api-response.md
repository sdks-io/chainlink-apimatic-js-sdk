
# Chain Api Response

*This model accepts additional fields of type unknown.*

## Structure

`ChainApiResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `metadata` | [`ChainMetadata`](../../doc/models/chain-metadata.md) | Required | - |
| `data` | [`Data`](../../doc/models/data.md) | Required | Chain details grouped by chain family |
| `ignored` | [`ChainConfigError[]`](../../doc/models/chain-config-error.md) | Required | List of chains that could not be configured |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import {
  ChainApiResponse,
  ChainFamily,
  ChainType,
  MEnvironment,
  SearchType,
} from 'chainlink-apimatic-sdk';

const chainApiResponse: ChainApiResponse = {
  metadata: {
    environment: MEnvironment.Mainnet,
    timestamp: '2016-03-13T12:52:32.123Z',
    requestId: '000009f4-0000-0000-0000-000000000000',
    ignoredChainCount: 134,
    validChainCount: 148,
    searchQuery: 'searchQuery4',
    searchType: SearchType.Selector,
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  data: {
    evm: {
      'key0': {
        chainId: 136,
        displayName: 'displayName2',
        selector: 'selector6',
        internalId: 'internalId8',
        feeTokens: [
          'String4',
          'String5'
        ],
        router: 'router4',
        rmn: 'rmn0',
        chainType: ChainType.Sui,
        chainFamily: ChainFamily.Canton,
        supported: false,
        registryModule: 'registryModule8',
        tokenAdminRegistry: 'tokenAdminRegistry0',
        tokenPoolFactory: 'tokenPoolFactory8',
        feeQuoter: 'feeQuoter2',
        mcms: 'mcms8',
        additionalProperties: {
          'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
        },
      }
    },
    solana: {
      'key0': {
        chainId: 10,
        displayName: 'displayName8',
        selector: 'selector6',
        internalId: 'internalId8',
        feeTokens: [
          'String4',
          'String5'
        ],
        router: 'router4',
        rmn: 'rmn0',
        chainType: ChainType.Tron,
        chainFamily: ChainFamily.Canton,
        supported: false,
        registryModule: 'registryModule2',
        tokenAdminRegistry: 'tokenAdminRegistry0',
        tokenPoolFactory: 'tokenPoolFactory8',
        feeQuoter: 'feeQuoter2',
        mcms: 'mcms8',
        additionalProperties: {
          'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
        },
      },
      'key1': {
        chainId: 10,
        displayName: 'displayName8',
        selector: 'selector6',
        internalId: 'internalId8',
        feeTokens: [
          'String4',
          'String5'
        ],
        router: 'router4',
        rmn: 'rmn0',
        chainType: ChainType.Tron,
        chainFamily: ChainFamily.Canton,
        supported: false,
        registryModule: 'registryModule2',
        tokenAdminRegistry: 'tokenAdminRegistry0',
        tokenPoolFactory: 'tokenPoolFactory8',
        feeQuoter: 'feeQuoter2',
        mcms: 'mcms8',
        additionalProperties: {
          'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
        },
      },
      'key2': {
        chainId: 10,
        displayName: 'displayName8',
        selector: 'selector6',
        internalId: 'internalId8',
        feeTokens: [
          'String4',
          'String5'
        ],
        router: 'router4',
        rmn: 'rmn0',
        chainType: ChainType.Tron,
        chainFamily: ChainFamily.Canton,
        supported: false,
        registryModule: 'registryModule2',
        tokenAdminRegistry: 'tokenAdminRegistry0',
        tokenPoolFactory: 'tokenPoolFactory8',
        feeQuoter: 'feeQuoter2',
        mcms: 'mcms8',
        additionalProperties: {
          'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
        },
      }
    },
    aptos: {
      'key0': {
        chainId: 64,
        displayName: 'displayName6',
        selector: 'selector8',
        internalId: 'internalId0',
        feeTokens: [
          'String2',
          'String3',
          'String4'
        ],
        router: 'router6',
        rmn: 'rmn8',
        chainType: ChainType.Solana,
        chainFamily: ChainFamily.Solana,
        supported: false,
        registryModule: 'registryModule0',
        tokenAdminRegistry: 'tokenAdminRegistry2',
        tokenPoolFactory: 'tokenPoolFactory0',
        feeQuoter: 'feeQuoter4',
        mcms: 'mcms0',
        additionalProperties: {
          'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
        },
      },
      'key1': {
        chainId: 64,
        displayName: 'displayName6',
        selector: 'selector8',
        internalId: 'internalId0',
        feeTokens: [
          'String2',
          'String3',
          'String4'
        ],
        router: 'router6',
        rmn: 'rmn8',
        chainType: ChainType.Solana,
        chainFamily: ChainFamily.Solana,
        supported: false,
        registryModule: 'registryModule0',
        tokenAdminRegistry: 'tokenAdminRegistry2',
        tokenPoolFactory: 'tokenPoolFactory0',
        feeQuoter: 'feeQuoter4',
        mcms: 'mcms0',
        additionalProperties: {
          'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
        },
      }
    },
    sui: {
      'key0': {
        chainId: 216,
        displayName: 'displayName4',
        selector: 'selector0',
        internalId: 'internalId2',
        feeTokens: [
          'String0',
          'String1'
        ],
        router: 'router8',
        rmn: 'rmn6',
        chainType: ChainType.Tron,
        chainFamily: ChainFamily.Canton,
        supported: false,
        registryModule: 'registryModule8',
        tokenAdminRegistry: 'tokenAdminRegistry4',
        tokenPoolFactory: 'tokenPoolFactory2',
        feeQuoter: 'feeQuoter6',
        mcms: 'mcms2',
        additionalProperties: {
          'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
        },
      }
    },
    tron: {
      'key0': {
        chainId: 140,
        displayName: 'displayName2',
        selector: 'selector2',
        internalId: 'internalId4',
        feeTokens: [
          'String8',
          'String9'
        ],
        router: 'router0',
        rmn: 'rmn6',
        chainType: ChainType.Tron,
        chainFamily: ChainFamily.Starknet,
        supported: false,
        registryModule: 'registryModule6',
        tokenAdminRegistry: 'tokenAdminRegistry6',
        tokenPoolFactory: 'tokenPoolFactory4',
        feeQuoter: 'feeQuoter8',
        mcms: 'mcms4',
        additionalProperties: {
          'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
        },
      }
    },
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  ignored: [
    {
      chainId: 192,
      networkId: 'networkId6',
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

