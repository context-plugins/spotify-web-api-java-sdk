
# Cursor Object

*This model accepts additional fields of type Object.*

## Structure

`CursorObject`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `After` | `String` | Optional | The cursor to use as key to find the next page of items. | String getAfter() | setAfter(String after) |
| `Before` | `String` | Optional | The cursor to use as key to find the previous page of items. | String getBefore() | setBefore(String before) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.models.CursorObject;
import java.io.IOException;

CursorObject cursorObject = new CursorObject.Builder()
    .after("after0")
    .before("before8")
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

