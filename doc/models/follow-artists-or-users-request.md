
# Follow Artists or Users Request

*This model accepts additional fields of type Object.*

## Structure

`FollowArtistsOrUsersRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Ids` | `List<String>` | Required | A JSON array of the artist or user [Spotify IDs](https://developer.spotify.com/documentation/web-api/concepts/spotify-uris-ids).<br>For example: `{ids:["74ASZWbe4lXaubB36ztrGX", "08td7MxkoHQkXnWAYD8d6Q"]}`. A maximum of 50 IDs can be sent in one request. _**Note**: if the `ids` parameter is present in the query string, any IDs listed here in the body will be ignored._ | List<String> getIds() | setIds(List<String> ids) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.models.FollowArtistsOrUsersRequest;
import java.io.IOException;
import java.util.Arrays;

FollowArtistsOrUsersRequest followArtistsOrUsersRequest = new FollowArtistsOrUsersRequest.Builder(
    Arrays.asList(
        "ids1",
        "ids2"
    )
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

