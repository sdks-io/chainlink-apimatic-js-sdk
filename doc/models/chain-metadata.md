
# Chain Metadata

*This model accepts additional fields of type unknown.*

## Structure

`ChainMetadata`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `environment` | [`MEnvironment`](../../doc/models/m-environment.md) | Required | The network environment |
| `timestamp` | `string` | Required | ISO timestamp of the response |
| `requestId` | `string` | Required | Unique identifier for the request |
| `ignoredChainCount` | `number` | Required | Number of chains ignored due to configuration issues<br><br>**Constraints**: `>= 0` |
| `validChainCount` | `number` | Required | Number of valid chains in the response<br><br>**Constraints**: `>= 0` |
| `searchQuery` | `string \| undefined` | Optional | The search query that was used (only present when search parameter was provided) |
| `searchType` | [`SearchType \| undefined`](../../doc/models/search-type.md) | Optional | The detected type of search query. 'selector' for CCIP selectors (>17 digits), 'chainId' for chain IDs (≤17 digits or Solana base58), 'internalId' for kebab-case identifiers, 'displayName' for fuzzy text search. |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import {
  ChainMetadata,
  MEnvironment,
  SearchType,
} from 'chainlink-apimatic-sdk';

const chainMetadata: ChainMetadata = {
  environment: MEnvironment.Mainnet,
  timestamp: '2016-03-13T12:52:32.123Z',
  requestId: '0000086e-0000-0000-0000-000000000000',
  ignoredChainCount: 0,
  validChainCount: 14,
  searchQuery: 'searchQuery4',
  searchType: SearchType.InternalId,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

