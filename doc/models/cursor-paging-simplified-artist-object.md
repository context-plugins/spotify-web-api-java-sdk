
# Cursor Paging Simplified Artist Object

*This model accepts additional fields of type Object.*

## Structure

`CursorPagingSimplifiedArtistObject`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Href` | `String` | Optional | A link to the Web API endpoint returning the full result of the request. | String getHref() | setHref(String href) |
| `Limit` | `Integer` | Optional | The maximum number of items in the response (as set in the query or by default). | Integer getLimit() | setLimit(Integer limit) |
| `Next` | `String` | Optional | URL to the next page of items. ( `null` if none) | String getNext() | setNext(String next) |
| `Cursors` | [`CursorObject`](../../doc/models/cursor-object.md) | Optional | - | CursorObject getCursors() | setCursors(CursorObject cursors) |
| `Total` | `Integer` | Optional | The total number of items available to return. | Integer getTotal() | setTotal(Integer total) |
| `Items` | [`List<ArtistObject>`](../../doc/models/artist-object.md) | Optional | - | List<ArtistObject> getItems() | setItems(List<ArtistObject> items) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.models.CursorObject;
import com.spotify.api.models.CursorPagingSimplifiedArtistObject;
import java.io.IOException;

CursorPagingSimplifiedArtistObject cursorPagingSimplifiedArtistObject = new CursorPagingSimplifiedArtistObject.Builder()
    .href("href2")
    .limit(24)
    .next("next2")
    .cursors(new CursorObject.Builder()
        .after("after8")
        .before("before6")
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build())
    .total(118)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

