
# Error Object

*This model accepts additional fields of type Object.*

## Structure

`ErrorObject`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Status` | `int` | Required | The HTTP status code (also returned in the response header; see [Response Status Codes](https://developer.spotify.com/documentation/web-api/concepts/api-calls#response-status-codes) for more information).<br><br>**Constraints**: `>= 400`, `<= 599` | int getStatus() | setStatus(int status) |
| `Message` | `String` | Required | A short description of the cause of the error. | String getMessage() | setMessage(String message) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.models.ErrorObject;
import java.io.IOException;

ErrorObject errorObject = new ErrorObject.Builder(
    400,
    "message2"
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

