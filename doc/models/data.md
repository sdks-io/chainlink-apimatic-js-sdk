
# Data

Chain details grouped by chain family

*This model accepts additional fields of type unknown.*

## Structure

`Data`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `evm` | [`Record<string, ChainDetails> \| undefined`](../../doc/models/chain-details.md) | Optional | EVM chain details keyed by the specified output key |
| `solana` | [`Record<string, ChainDetails> \| undefined`](../../doc/models/chain-details.md) | Optional | Solana chain details keyed by the specified output key |
| `aptos` | [`Record<string, ChainDetails> \| undefined`](../../doc/models/chain-details.md) | Optional | Aptos chain details keyed by the specified output key |
| `sui` | [`Record<string, ChainDetails> \| undefined`](../../doc/models/chain-details.md) | Optional | Sui chain details keyed by the specified output key |
| `tron` | [`Record<string, ChainDetails> \| undefined`](../../doc/models/chain-details.md) | Optional | Tron chain details keyed by the specified output key |
| `canton` | [`Record<string, ChainDetails> \| undefined`](../../doc/models/chain-details.md) | Optional | Canton chain details keyed by the specified output key |
| `ton` | [`Record<string, ChainDetails> \| undefined`](../../doc/models/chain-details.md) | Optional | TON chain details keyed by the specified output key |
| `stellar` | [`Record<string, ChainDetails> \| undefined`](../../doc/models/chain-details.md) | Optional | Stellar chain details keyed by the specified output key |
| `starknet` | [`Record<string, ChainDetails> \| undefined`](../../doc/models/chain-details.md) | Optional | Starknet chain details keyed by the specified output key |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { ChainFamily, ChainType, Data } from 'chainlink-apimatic-sdk';

const data: Data = {
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
};
```

