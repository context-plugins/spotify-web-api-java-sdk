
# Too Many Requests 1 Exception

*This model accepts additional fields of type Object.*

## Structure

`TooManyRequests1Exception`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Error` | [`ErrorObject`](../../doc/models/error-object.md) | Required | - | ErrorObject getError() | setError(ErrorObject error) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
try {
    // make the API call
} catch (TooManyRequests1Exception e) {
    e.printStackTrace();
} catch (ApiException e) {
    e.printStackTrace();
}
```

