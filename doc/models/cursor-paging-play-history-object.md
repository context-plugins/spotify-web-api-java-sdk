
# Cursor Paging Play History Object

*This model accepts additional fields of type Object.*

## Structure

`CursorPagingPlayHistoryObject`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Href` | `String` | Optional | A link to the Web API endpoint returning the full result of the request. | String getHref() | setHref(String href) |
| `Limit` | `Integer` | Optional | The maximum number of items in the response (as set in the query or by default). | Integer getLimit() | setLimit(Integer limit) |
| `Next` | `String` | Optional | URL to the next page of items. ( `null` if none) | String getNext() | setNext(String next) |
| `Cursors` | [`CursorObject`](../../doc/models/cursor-object.md) | Optional | - | CursorObject getCursors() | setCursors(CursorObject cursors) |
| `Total` | `Integer` | Optional | The total number of items available to return. | Integer getTotal() | setTotal(Integer total) |
| `Items` | [`List<PlayHistoryObject>`](../../doc/models/play-history-object.md) | Optional | - | List<PlayHistoryObject> getItems() | setItems(List<PlayHistoryObject> items) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.models.CursorObject;
import com.spotify.api.models.CursorPagingPlayHistoryObject;
import java.io.IOException;

CursorPagingPlayHistoryObject cursorPagingPlayHistoryObject = new CursorPagingPlayHistoryObject.Builder()
    .href("href2")
    .limit(124)
    .next("next8")
    .cursors(new CursorObject.Builder()
        .after("after8")
        .before("before6")
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build())
    .total(218)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

