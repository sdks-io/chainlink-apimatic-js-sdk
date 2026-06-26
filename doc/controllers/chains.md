# Chains

Chain information endpoints

```ts
const chainsApi = new ChainsApi(client);
```

## Class Name

`ChainsApi`


# Get Chains

Returns information about Cross-Chain Interoperability Protocol (CCIP) chains across different blockchain families (EVM, Solana, Aptos)

```ts
async getChains(
  environment: Environment3,
  chainId?: string,
  selector?: string,
  internalId?: string,
  outputKey?: OutputKey,
  enrichFeeTokens?: EnrichFeeTokens,
  search?: string,
  family?: Family,
  requestOptions?: RequestOptions
): Promise<ApiResponse<ChainApiResponse>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `environment` | [`Environment3`](../../doc/models/environment-3.md) | Query, Required | The network environment to query |
| `chainId` | `string \| undefined` | Query, Optional | Filter by chain ID (e.g., "1" for Ethereum, "56" for BSC, or a Solana pubkey) |
| `selector` | `string \| undefined` | Query, Optional | Filter by CCIP chain selector. Multiple selectors can be specified using comma-separated values |
| `internalId` | `string \| undefined` | Query, Optional | Filter by internal chain identifier. Multiple IDs can be specified using comma-separated values (e.g., "ethereum-mainnet,bsc-mainnet") |
| `outputKey` | [`OutputKey \| undefined`](../../doc/models/output-key.md) | Query, Optional | Key to use for organizing the response data<br><br>**Default**: `OutputKey.ChainId` |
| `enrichFeeTokens` | [`EnrichFeeTokens \| undefined`](../../doc/models/enrich-fee-tokens.md) | Query, Optional | When set to 'true', returns detailed fee token information including addresses, names, and decimals instead of just symbol strings<br><br>**Default**: `EnrichFeeTokens.False` |
| `search` | `string \| undefined` | Query, Optional | Unified search query. Automatically detects query type: selector (>17 digits), chainId (≤17 digits or Solana base58 hash), internalId (kebab-case), or displayName (fuzzy text search). Cannot be combined with chainId, selector, or internalId filters.<br><br>**Constraints**: *Maximum Length*: `100` |
| `family` | [`Family \| undefined`](../../doc/models/family.md) | Query, Optional | Filter results by chain family. Only effective when using the search parameter. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**: Successful response with chain data

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`ChainApiResponse`](../../doc/models/chain-api-response.md).

## Example Usage

```ts
const environment = Environment3.Mainnet;

const chainId = '1,56';

const selector = '5009297550715157269,13264668187771770619';

const internalId = 'ethereum-mainnet,bsc-mainnet';

const outputKey = OutputKey.ChainId;

const enrichFeeTokens = EnrichFeeTokens.False;

const search = 'ethereum';

try {
  const response = await chainsApi.getChains(
    environment,
    chainId,
    selector,
    internalId,
    outputKey,
    enrichFeeTokens,
    search
  );

  // Extracting fully parsed response body.
  console.log(response.result);

  // Extracting response status code.
  console.log(response.statusCode);
  // Extracting response headers.
  console.log(response.headers);
  // Extracting response body of type `string | Stream`
  console.log(response.body);
} catch (error) {
  if (error instanceof ApiError) {
    // Extracting response error status code.
    console.log(error.statusCode);
    // Extracting response error headers.
    console.log(error.headers);
    // Extracting response error body of type `string | Stream`.
    console.log(error.body);
    if (error instanceof ErrorResponseError) {
      console.log(error.result);
    }
  }
}
```

## Example Response *(as JSON)*

```json
{
  "metadata": {
    "environment": "mainnet",
    "timestamp": "2024-03-14T12:00:00Z",
    "requestId": "123e4567-e89b-12d3-a456-426614174000",
    "ignoredChainCount": 0,
    "validChainCount": 2
  },
  "data": {
    "evm": {
      "1": {
        "chainId": 1,
        "displayName": "Ethereum",
        "selector": "5009297550715157269",
        "internalId": "ethereum-mainnet",
        "feeTokens": [
          "LINK",
          "WETH",
          "GHO"
        ],
        "router": "0x80226fc0Ee2b096224EeAc085Bb9a8cba1146f7D",
        "rmn": "0x411dE17f12D1A34ecC7F45f49844626267c75e81",
        "registryModule": "0x13022e3e6C77524308BD56AEd716E88311b2E533",
        "tokenAdminRegistry": "0xb22764f98dD05c789929716D677382Df22C05Cb6",
        "tokenPoolFactory": "0x17D8a409fE2ceF2d3808bcB61F14aBEFfc28876e",
        "chainType": "evm",
        "chainFamily": "evm",
        "supported": true
      }
    },
    "solana": {
      "solana-devnet": {
        "chainId": "solana-devnet",
        "displayName": "Solana Devnet",
        "selector": "16015286601757825753",
        "internalId": "solana-devnet",
        "feeTokens": [
          "LINK",
          "SOL"
        ],
        "router": "CCiPv7hcmEqNdMdJgmHDJmEJyCkBgLqxmcf87R1Gho6H",
        "rmn": "CRmNVnB7S6SqEPFG6m9dVp9fJJCjr3TC2TiAWB3RqNod",
        "feeQuoter": "FqbCVbS7a4ndxs9xZ8UmfL6LQsUhAJNkWxW3duJRrCWD",
        "chainType": "solana",
        "chainFamily": "solana",
        "supported": true
      }
    }
  },
  "ignored": []
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid request parameters | [`ErrorResponseError`](../../doc/models/error-response-error.md) |
| 500 | Internal server error | [`ErrorResponseError`](../../doc/models/error-response-error.md) |

