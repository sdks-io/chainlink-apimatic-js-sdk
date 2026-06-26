# Lanes

Cross-chain lane information endpoints

```ts
const lanesApi = new LanesApi(client);
```

## Class Name

`LanesApi`


# Get Lanes

Returns information about Cross-Chain Interoperability Protocol (CCIP) lanes between supported chains. Each lane represents a unidirectional connection from a source chain to a destination chain, with associated onRamp and offRamp contracts and supported tokens.

```ts
async getLanes(
  environment: Environment3,
  sourceChainId?: string,
  destinationChainId?: string,
  sourceSelector?: string,
  destinationSelector?: string,
  sourceInternalId?: string,
  destinationInternalId?: string,
  version?: string,
  outputKey?: OutputKey,
  requestOptions?: RequestOptions
): Promise<ApiResponse<LaneApiResponse>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `environment` | [`Environment3`](../../doc/models/environment-3.md) | Query, Required | The network environment to query |
| `sourceChainId` | `string \| undefined` | Query, Optional | Filter by source chain ID. Multiple chain IDs can be specified using comma-separated values |
| `destinationChainId` | `string \| undefined` | Query, Optional | Filter by destination chain ID. Multiple chain IDs can be specified using comma-separated values |
| `sourceSelector` | `string \| undefined` | Query, Optional | Filter by source chain CCIP selector. Multiple selectors can be specified using comma-separated values |
| `destinationSelector` | `string \| undefined` | Query, Optional | Filter by destination chain CCIP selector. Multiple selectors can be specified using comma-separated values |
| `sourceInternalId` | `string \| undefined` | Query, Optional | Filter by source chain internal identifier. Multiple IDs can be specified using comma-separated values |
| `destinationInternalId` | `string \| undefined` | Query, Optional | Filter by destination chain internal identifier. Multiple IDs can be specified using comma-separated values |
| `version` | `string \| undefined` | Query, Optional | Filter by lane version. Only lanes where both onRamp and offRamp match the specified version will be returned |
| `outputKey` | [`OutputKey \| undefined`](../../doc/models/output-key.md) | Query, Optional | Key format to use for organizing the lane keys in the response<br><br>**Default**: `OutputKey.ChainId` |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**: Successful response with lane data

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`LaneApiResponse`](../../doc/models/lane-api-response.md).

## Example Usage

```ts
const environment = Environment3.Mainnet;

const sourceChainId = '1,56';

const destinationChainId = '137,42161';

const sourceSelector = '5009297550715157269';

const destinationSelector = '4949039107694359620';

const sourceInternalId = 'ethereum-mainnet';

const destinationInternalId = 'polygon-mainnet';

const version = '1.6.0';

const outputKey = OutputKey.ChainId;

try {
  const response = await lanesApi.getLanes(
    environment,
    sourceChainId,
    destinationChainId,
    sourceSelector,
    destinationSelector,
    sourceInternalId,
    destinationInternalId,
    version,
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

## Example Response *(as JSON)*

```json
{
  "metadata": {
    "environment": "mainnet",
    "timestamp": "2024-01-15T10:30:00Z",
    "requestId": "123e4567-e89b-12d3-a456-426614174000",
    "ignoredLaneCount": 0,
    "validLaneCount": 2
  },
  "data": {
    "1_to_56": {
      "sourceChain": {
        "chainId": 1,
        "displayName": "Ethereum Mainnet",
        "selector": "5009297550715157269",
        "internalId": "ethereum-mainnet"
      },
      "destinationChain": {
        "chainId": 56,
        "displayName": "BNB Smart Chain",
        "selector": "13264668187771770619",
        "internalId": "bsc-mainnet"
      },
      "onRamp": {
        "address": "0x925228D7B82d883Dde340A55Fe8e6dA56244A22C",
        "version": "1.6.0",
        "enforceOutOfOrder": false
      },
      "offRamp": {
        "address": "0xdf85c8381954694E74abD07488f452b374A4B4cC",
        "version": "1.6.0"
      },
      "supportedTokens": [
        "LINK",
        "CCIP-BnM",
        "USDC"
      ]
    },
    "1_to_137": {
      "sourceChain": {
        "chainId": 1,
        "displayName": "Ethereum Mainnet",
        "selector": "5009297550715157269",
        "internalId": "ethereum-mainnet"
      },
      "destinationChain": {
        "chainId": 137,
        "displayName": "Polygon Mainnet",
        "selector": "4051577828743386545",
        "internalId": "polygon-mainnet"
      },
      "onRamp": {
        "address": "0x3df8dAe2d123081c4D5E946E655F7c109B9Dd630",
        "version": "1.5.0"
      },
      "offRamp": {
        "address": "0x0af338C8545eb6265FedC01BEca4cAe0d94DA9Da",
        "version": "1.5.0"
      },
      "supportedTokens": [
        "LINK",
        "USDC"
      ]
    }
  },
  "ignored": []
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad request - invalid parameters | [`ErrorResponseError`](../../doc/models/error-response-error.md) |
| 500 | Internal server error | [`ErrorResponseError`](../../doc/models/error-response-error.md) |

