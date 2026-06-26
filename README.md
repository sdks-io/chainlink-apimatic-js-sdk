
# Getting Started with CCIP directory and configuration REST API (v1)

## Introduction

**Deprecation:** This CCIP Directory and configuration REST API (v1), including `/api/ccip/v1/*` on docs.chain.link, is **planned for deprecation soon**. Timelines and migration guidance will be published in the [CCIP Tools documentation](https://docs.chain.link/ccip/tools/). For new integrations, prefer the [CCIP Tools REST API (v2)](https://docs.chain.link/ccip/tools/api/) where it meets your needs.

REST API for CCIP supported chains, tokens, lanes, and related configuration on docs.chain.link. This is distinct from the CCIP Tools REST API (v2), which covers messages, lane latency, intents, and related tooling (https://docs.chain.link/ccip/tools/api/). For on-chain Solidity, Move, SVM, and TON interfaces, see https://docs.chain.link/ccip/api-reference.

To get started quickly, you can download our [Postman Collection](/api/ccip/v1/postman-collection.json) which includes all endpoints and example requests.

## Install the Package

Run the following command from your project directory to install the package from npm:

```bash
npm install chainlink-apimatic-sdk@0.0.2
```

For additional package details, see the [Npm page for the chainlink-apimatic-sdk@0.0.2 npm](https://www.npmjs.com/package/chainlink-apimatic-sdk/v/0.0.2).

## Initialize the API Client

**_Note:_** Documentation for the client can be found [here.](https://www.github.com/sdks-io/chainlink-apimatic-js-sdk/tree/0.0.2/doc/client.md)

The following parameters are configurable for the API Client:

| Parameter | Type | Description |
|  --- | --- | --- |
| environment | [`Environment`](https://www.github.com/sdks-io/chainlink-apimatic-js-sdk/tree/0.0.2/README.md#environments) | The API environment. <br> **Default: `Environment.Production`** |
| timeout | `number` | Timeout for API calls.<br>*Default*: `30000` |
| httpClientOptions | [`Partial<HttpClientOptions>`](https://www.github.com/sdks-io/chainlink-apimatic-js-sdk/tree/0.0.2/doc/http-client-options.md) | Stable configurable http client options. |
| unstableHttpClientOptions | `any` | Unstable configurable http client options. |
| logging | [`PartialLoggingOptions`](https://www.github.com/sdks-io/chainlink-apimatic-js-sdk/tree/0.0.2/doc/partial-logging-options.md) | Logging Configuration to enable logging |

The API client can be initialized as follows:

### Code-Based Client Initialization

```ts
import { Client, Environment, LogLevel } from 'chainlink-apimatic-sdk';

const client = new Client({
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

See the [Configuration-Based Client Initialization](https://www.github.com/sdks-io/chainlink-apimatic-js-sdk/tree/0.0.2/doc/configuration-based-client-initialization.md) section for details.

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

See the [Environment-Based Client Initialization](https://www.github.com/sdks-io/chainlink-apimatic-js-sdk/tree/0.0.2/doc/environment-based-client-initialization.md) section for details.

## Environments

The SDK can be configured to use a different environment for making API calls. Available environments are:

### Fields

| Name | Description |
|  --- | --- |
| Production | **Default** Production server |
| Environment2 | Development server |

## List of APIs

* [Chains](https://www.github.com/sdks-io/chainlink-apimatic-js-sdk/tree/0.0.2/doc/controllers/chains.md)
* [Tokens](https://www.github.com/sdks-io/chainlink-apimatic-js-sdk/tree/0.0.2/doc/controllers/tokens.md)
* [Lanes](https://www.github.com/sdks-io/chainlink-apimatic-js-sdk/tree/0.0.2/doc/controllers/lanes.md)

## SDK Infrastructure

### Configuration

* [HttpClientOptions](https://www.github.com/sdks-io/chainlink-apimatic-js-sdk/tree/0.0.2/doc/http-client-options.md)
* [RetryConfiguration](https://www.github.com/sdks-io/chainlink-apimatic-js-sdk/tree/0.0.2/doc/retry-configuration.md)
* [ProxySettings](https://www.github.com/sdks-io/chainlink-apimatic-js-sdk/tree/0.0.2/doc/proxy-settings.md)
* [Configuration-Based Client Initialization](https://www.github.com/sdks-io/chainlink-apimatic-js-sdk/tree/0.0.2/doc/configuration-based-client-initialization.md)
* [Environment-Based Client Initialization](https://www.github.com/sdks-io/chainlink-apimatic-js-sdk/tree/0.0.2/doc/environment-based-client-initialization.md)
* [PartialLoggingOptions](https://www.github.com/sdks-io/chainlink-apimatic-js-sdk/tree/0.0.2/doc/partial-logging-options.md)
* [PartialRequestLoggingOptions](https://www.github.com/sdks-io/chainlink-apimatic-js-sdk/tree/0.0.2/doc/partial-request-logging-options.md)
* [PartialResponseLoggingOptions](https://www.github.com/sdks-io/chainlink-apimatic-js-sdk/tree/0.0.2/doc/partial-response-logging-options.md)
* [LoggerInterface](https://www.github.com/sdks-io/chainlink-apimatic-js-sdk/tree/0.0.2/doc/logger-interface.md)

### HTTP

* [HttpRequest](https://www.github.com/sdks-io/chainlink-apimatic-js-sdk/tree/0.0.2/doc/http-request.md)

### Utilities

* [ApiResponse](https://www.github.com/sdks-io/chainlink-apimatic-js-sdk/tree/0.0.2/doc/api-response.md)
* [ApiError](https://www.github.com/sdks-io/chainlink-apimatic-js-sdk/tree/0.0.2/doc/api-error.md)

