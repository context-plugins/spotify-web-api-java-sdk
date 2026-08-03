
# Playlists Followers Request

*This model accepts additional fields of type Object.*

## Structure

`PlaylistsFollowersRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Public` | `Boolean` | Optional | Defaults to `true`. If `true` the playlist will be included in user's public playlists, if `false` it will remain private. | Boolean getPublic() | setPublic(Boolean mPublic) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.models.PlaylistsFollowersRequest;
import java.io.IOException;

PlaylistsFollowersRequest playlistsFollowersRequest = new PlaylistsFollowersRequest.Builder()
    .mPublic(false)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

