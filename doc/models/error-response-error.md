
# Error Response Error

*This model accepts additional fields of type unknown.*

## Structure

`ErrorResponseError`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `error` | `string` | Required | Error type identifier |
| `message` | `string` | Required | Human-readable error message |
| `requestId` | `string \| undefined` | Optional | Unique identifier for the request, useful for debugging and support |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
try {
  // make the API call
} catch (error) {
  if (error instanceof ErrorResponseError) {
    console.log(error.result);
  }
}
```

