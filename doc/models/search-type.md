
# Search Type

The detected type of search query. 'selector' for CCIP selectors (>17 digits), 'chainId' for chain IDs (≤17 digits or Solana base58), 'internalId' for kebab-case identifiers, 'displayName' for fuzzy text search.

## Enumeration

`SearchType`

## Fields

| Name |
|  --- |
| `Selector` |
| `ChainId` |
| `InternalId` |
| `DisplayName` |

## Example

```ts
import { SearchType } from 'chainlink-apimatic-sdk';

const searchType = SearchType.InternalId;
```

