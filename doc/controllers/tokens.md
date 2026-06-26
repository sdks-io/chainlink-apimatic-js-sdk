# Tokens

Token information endpoints

```ts
const tokensApi = new TokensApi(client);
```

## Class Name

`TokensApi`


# Get Tokens

Returns information about Cross-Chain Interoperability Protocol (CCIP) supported tokens. The response includes token details organized by token symbol, with chain-specific information nested under each token and indexed by chain ID or selector (depending on the outputKey parameter).

```ts
async getTokens(
  environment: Environment3,
  tokenId?: string,
  chainId?: string,
  outputKey?: OutputKey,
  requestOptions?: RequestOptions
): Promise<ApiResponse<TokenApiResponse>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `environment` | [`Environment3`](../../doc/models/environment-3.md) | Query, Required | The network environment to query |
| `tokenId` | `string \| undefined` | Query, Optional | Filter by token canonical identifier (e.g., "LINK" for Chainlink token, or "LINK,ETH" for multiple tokens) |
| `chainId` | `string \| undefined` | Query, Optional | Filter by chain ID where the token is supported (e.g., "1" for Ethereum, or "1,56" for Ethereum and BSC) |
| `outputKey` | [`OutputKey \| undefined`](../../doc/models/output-key.md) | Query, Optional | Key to use for organizing the response data<br><br>**Default**: `OutputKey.ChainId` |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**: Successful response with token data

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`TokenApiResponse`](../../doc/models/token-api-response.md).

## Example Usage

```ts
const environment = Environment3.Mainnet;

const tokenId = 'LINK,ETH';

const chainId = '1,56';

const outputKey = OutputKey.ChainId;

try {
  const response = await tokensApi.getTokens(
    environment,
    tokenId,
    chainId,
    outputKey
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

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid request parameters | [`ErrorResponseError`](../../doc/models/error-response-error.md) |
| 500 | Internal server error | [`ErrorResponseError`](../../doc/models/error-response-error.md) |

