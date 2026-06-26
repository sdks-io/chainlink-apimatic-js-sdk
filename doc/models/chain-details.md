
# Chain Details

*This model accepts additional fields of type unknown.*

## Structure

`ChainDetails`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `chainId` | [`ChainDetailsChainId`](../../doc/models/containers/chain-details-chain-id.md) | Required | This is a container for one-of cases. |
| `displayName` | `string` | Required | Human-readable name of the chain. For supported chains, this comes from configuration. For unsupported chains, it is derived from the internalId. |
| `selector` | `string` | Required | CCIP chain selector |
| `internalId` | `string` | Required | Internal identifier for the chain |
| `feeTokens` | [`ChainDetailsFeeTokens`](../../doc/models/containers/chain-details-fee-tokens.md) | Required | This is a container for one-of cases. |
| `router` | `string` | Required | CCIP Router contract address. Empty string for unsupported chains. |
| `rmn` | `string` | Required | Risk Management Network contract address. Empty string for unsupported chains. |
| `chainType` | [`ChainType`](../../doc/models/chain-type.md) | Required | Type of blockchain |
| `chainFamily` | [`ChainFamily`](../../doc/models/chain-family.md) | Required | Blockchain family grouping |
| `supported` | `boolean` | Required | Whether this chain is fully supported with complete configuration. Unsupported chains have minimal details (empty router, rmn, feeTokens). |
| `registryModule` | `string \| undefined` | Optional | Registry Module contract address (EVM chains only) |
| `tokenAdminRegistry` | `string \| undefined` | Optional | Token Admin Registry contract address (EVM and Aptos chains) |
| `tokenPoolFactory` | `string \| undefined` | Optional | Token Pool Factory contract address (EVM chains only) |
| `feeQuoter` | `string \| undefined` | Optional | Fee Quoter address (Solana chains only) |
| `mcms` | `string \| undefined` | Optional | MCMS (Multi-Chain Management Service) address (Aptos chains only) |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { ChainDetails, ChainFamily, ChainType } from 'chainlink-apimatic-sdk';

const chainDetails: ChainDetails = {
  chainId: 176,
  displayName: 'displayName8',
  selector: 'selector6',
  internalId: 'internalId8',
  feeTokens: [
    'String4'
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
};
```

