
# Getting Started with Swagger Petstore - OpenAPI 3.0

## Introduction

This is a sample Pet Store Server based on the OpenAPI 3.0 specification.  You can find out more about
Swagger at [https://swagger.io](https://swagger.io). In the third iteration of the pet store, we've switched to the design first approach!
You can now help us improve the API whether it's by making changes to the definition itself or to the code.
That way, with time, we can improve the API in general, and expose some of the new features in OAS3.

Some useful links:

- [The Pet Store repository](https://github.com/swagger-api/swagger-petstore)
- [The source API definition for the Pet Store](https://github.com/swagger-api/swagger-petstore/blob/master/src/main/resources/openapi.yaml)

Find out more about Swagger: [https://swagger.io](https://swagger.io)

## Install the Package

Run the following command from your project directory to install the package from npm:

```bash
npm install chainlink-apimatic-sdk@0.0.1
```

For additional package details, see the [Npm page for the chainlink-apimatic-sdk@0.0.1 npm](https://www.npmjs.com/package/chainlink-apimatic-sdk/v/0.0.1).

## Initialize the API Client

**_Note:_** Documentation for the client can be found [here.](https://www.github.com/sdks-io/chainlink-apimatic-js-sdk/tree/0.0.1/doc/client.md)

The following parameters are configurable for the API Client:

| Parameter | Type | Description |
|  --- | --- | --- |
| environment | [`Environment`](https://www.github.com/sdks-io/chainlink-apimatic-js-sdk/tree/0.0.1/README.md#environments) | The API environment. <br> **Default: `Environment.Production`** |
| timeout | `number` | Timeout for API calls.<br>*Default*: `30000` |
| httpClientOptions | [`Partial<HttpClientOptions>`](https://www.github.com/sdks-io/chainlink-apimatic-js-sdk/tree/0.0.1/doc/http-client-options.md) | Stable configurable http client options. |
| unstableHttpClientOptions | `any` | Unstable configurable http client options. |
| logging | [`PartialLoggingOptions`](https://www.github.com/sdks-io/chainlink-apimatic-js-sdk/tree/0.0.1/doc/partial-logging-options.md) | Logging Configuration to enable logging |
| petstoreAuthCredentials | [`PetstoreAuthCredentials`](https://www.github.com/sdks-io/chainlink-apimatic-js-sdk/tree/0.0.1/doc/auth/oauth-2-implicit-grant.md) | The credential object for petstoreAuth |
| apiKeyCredentials | [`ApiKeyCredentials`](https://www.github.com/sdks-io/chainlink-apimatic-js-sdk/tree/0.0.1/doc/auth/custom-header-signature.md) | The credential object for apiKey |

The API client can be initialized as follows:

### Code-Based Client Initialization

```ts
import {
  Client,
  Environment,
  LogLevel,
  OauthScopePetstoreAuth,
} from 'chainlink-apimatic-sdk';

const client = new Client({
  petstoreAuthCredentials: {
    oauthClientId: 'OAuthClientId',
    oauthRedirectUri: 'OAuthRedirectUri',
    oauthScopes: [
      OauthScopePetstoreAuth.Writepets,
      OauthScopePetstoreAuth.Readpets
    ]
  },
  apiKeyCredentials: {
    'api_key': 'api_key'
  },
  timeout: 30000,
  environment: Environment.Production,
  logging: {
    logLevel: LogLevel.Info,
    logRequest: {
      logBody: true
    },
    logResponse: {
      logHeaders: true
    }
  },
});
```

### Configuration-Based Client Initialization

```ts
import * as path from 'path';
import * as fs from 'fs';
import { Client } from 'chainlink-apimatic-sdk';

// Provide absolute path for the configuration file
const absolutePath = path.resolve('./config.json');

// Read the configuration file content
const fileContent = fs.readFileSync(absolutePath, 'utf-8');

// Initialize client from JSON configuration content
const client = Client.fromJsonConfig(fileContent);
```

See the [Configuration-Based Client Initialization](https://www.github.com/sdks-io/chainlink-apimatic-js-sdk/tree/0.0.1/doc/configuration-based-client-initialization.md) section for details.

### Environment-Based Client Initialization

```ts
import * as dotenv from 'dotenv';
import * as path from 'path';
import * as fs from 'fs';
import { Client } from 'chainlink-apimatic-sdk';

// Optional - Provide absolute path for the .env file
const absolutePath = path.resolve('./.env');

if (fs.existsSync(absolutePath)) {
  // Load environment variables from .env file
  dotenv.config({ path: absolutePath, override: true });
}

// Initialize client using environment variables
const client = Client.fromEnvironment(process.env);
```

See the [Environment-Based Client Initialization](https://www.github.com/sdks-io/chainlink-apimatic-js-sdk/tree/0.0.1/doc/environment-based-client-initialization.md) section for details.

## Environments

The SDK can be configured to use a different environment for making API calls. Available environments are:

### Fields

| Name | Description |
|  --- | --- |
| Production | **Default** |

## Authorization

This API uses the following authentication schemes.

* [`petstore_auth (OAuth 2 Implicit Grant)`](https://www.github.com/sdks-io/chainlink-apimatic-js-sdk/tree/0.0.1/doc/auth/oauth-2-implicit-grant.md)
* [`api_key (Custom Header Signature)`](https://www.github.com/sdks-io/chainlink-apimatic-js-sdk/tree/0.0.1/doc/auth/custom-header-signature.md)

## List of APIs

* [Pet](https://www.github.com/sdks-io/chainlink-apimatic-js-sdk/tree/0.0.1/doc/controllers/pet.md)
* [Store](https://www.github.com/sdks-io/chainlink-apimatic-js-sdk/tree/0.0.1/doc/controllers/store.md)
* [User](https://www.github.com/sdks-io/chainlink-apimatic-js-sdk/tree/0.0.1/doc/controllers/user.md)

## SDK Infrastructure

### Configuration

* [HttpClientOptions](https://www.github.com/sdks-io/chainlink-apimatic-js-sdk/tree/0.0.1/doc/http-client-options.md)
* [RetryConfiguration](https://www.github.com/sdks-io/chainlink-apimatic-js-sdk/tree/0.0.1/doc/retry-configuration.md)
* [ProxySettings](https://www.github.com/sdks-io/chainlink-apimatic-js-sdk/tree/0.0.1/doc/proxy-settings.md)
* [Configuration-Based Client Initialization](https://www.github.com/sdks-io/chainlink-apimatic-js-sdk/tree/0.0.1/doc/configuration-based-client-initialization.md)
* [Environment-Based Client Initialization](https://www.github.com/sdks-io/chainlink-apimatic-js-sdk/tree/0.0.1/doc/environment-based-client-initialization.md)
* [PartialLoggingOptions](https://www.github.com/sdks-io/chainlink-apimatic-js-sdk/tree/0.0.1/doc/partial-logging-options.md)
* [PartialRequestLoggingOptions](https://www.github.com/sdks-io/chainlink-apimatic-js-sdk/tree/0.0.1/doc/partial-request-logging-options.md)
* [PartialResponseLoggingOptions](https://www.github.com/sdks-io/chainlink-apimatic-js-sdk/tree/0.0.1/doc/partial-response-logging-options.md)
* [LoggerInterface](https://www.github.com/sdks-io/chainlink-apimatic-js-sdk/tree/0.0.1/doc/logger-interface.md)

### HTTP

* [HttpRequest](https://www.github.com/sdks-io/chainlink-apimatic-js-sdk/tree/0.0.1/doc/http-request.md)

### Utilities

* [ApiResponse](https://www.github.com/sdks-io/chainlink-apimatic-js-sdk/tree/0.0.1/doc/api-response.md)
* [ApiError](https://www.github.com/sdks-io/chainlink-apimatic-js-sdk/tree/0.0.1/doc/api-error.md)

