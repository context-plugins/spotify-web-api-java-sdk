
# Remove Shows Request

*This model accepts additional fields of type Object.*

## Structure

`RemoveShowsRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Ids` | `List<String>` | Optional | A JSON array of the [Spotify IDs](https://developer.spotify.comhttps://developer.spotify.com/documentation/web-api/#spotify-uris-and-ids).  <br>A maximum of 50 items can be specified in one request. *Note: if the `ids` parameter is present in the query string, any IDs listed here in the body will be ignored.* | List<String> getIds() | setIds(List<String> ids) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.models.RemoveShowsRequest;
import java.io.IOException;
import java.util.Arrays;

RemoveShowsRequest removeShowsRequest = new RemoveShowsRequest.Builder()
    .ids(Arrays.asList(
        "ids1"
    ))
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

