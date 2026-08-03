
# Cursor Paging Object

*This model accepts additional fields of type Object.*

## Structure

`CursorPagingObject`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Href` | `String` | Optional | A link to the Web API endpoint returning the full result of the request. | String getHref() | setHref(String href) |
| `Limit` | `Integer` | Optional | The maximum number of items in the response (as set in the query or by default). | Integer getLimit() | setLimit(Integer limit) |
| `Next` | `String` | Optional | URL to the next page of items. ( `null` if none) | String getNext() | setNext(String next) |
| `Cursors` | [`CursorObject`](../../doc/models/cursor-object.md) | Optional | - | CursorObject getCursors() | setCursors(CursorObject cursors) |
| `Total` | `Integer` | Optional | The total number of items available to return. | Integer getTotal() | setTotal(Integer total) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.models.CursorObject;
import com.spotify.api.models.CursorPagingObject;
import java.io.IOException;

CursorPagingObject cursorPagingObject = new CursorPagingObject.Builder()
    .href("href8")
    .limit(82)
    .next("next6")
    .cursors(new CursorObject.Builder()
        .after("after8")
        .before("before6")
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build())
    .total(176)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

