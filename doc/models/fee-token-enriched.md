
# Fee Token Enriched

*This model accepts additional fields of type unknown.*

## Structure

`FeeTokenEnriched`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `symbol` | `string` | Required | Token symbol (e.g., LINK, WETH) |
| `name` | `string` | Required | Token name (e.g., Chainlink, Wrapped Ether) |
| `address` | `string` | Required | Token contract address on this chain |
| `decimals` | `number` | Required | Number of decimals for the token<br><br>**Constraints**: `>= 0`, `<= 18` |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { FeeTokenEnriched } from 'chainlink-apimatic-sdk';

const feeTokenEnriched: FeeTokenEnriched = {
  symbol: 'symbol6',
  name: 'name4',
  address: 'address0',
  decimals: 18,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

