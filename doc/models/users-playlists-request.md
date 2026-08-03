
# Users Playlists Request

*This model accepts additional fields of type Object.*

## Structure

`UsersPlaylistsRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Name` | `String` | Required | The name for the new playlist, for example `"Your Coolest Playlist"`. This name does not need to be unique; a user may have several playlists with the same name. | String getName() | setName(String name) |
| `Public` | `Boolean` | Optional | Defaults to `true`. If `true` the playlist will be public, if `false` it will be private. To be able to create private playlists, the user must have granted the `playlist-modify-private` [scope](https://developer.spotify.com/documentation/web-api/concepts/scopes/#list-of-scopes) | Boolean getPublic() | setPublic(Boolean mPublic) |
| `Collaborative` | `Boolean` | Optional | Defaults to `false`. If `true` the playlist will be collaborative. _**Note**: to create a collaborative playlist you must also set `public` to `false`. To create collaborative playlists you must have granted `playlist-modify-private` and `playlist-modify-public` [scopes](https://developer.spotify.com/documentation/web-api/concepts/scopes/#list-of-scopes)._ | Boolean getCollaborative() | setCollaborative(Boolean collaborative) |
| `Description` | `String` | Optional | value for playlist description as displayed in Spotify Clients and in the Web API. | String getDescription() | setDescription(String description) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.models.UsersPlaylistsRequest;
import java.io.IOException;

UsersPlaylistsRequest usersPlaylistsRequest = new UsersPlaylistsRequest.Builder(
    "New Playlist"
)
.mPublic(false)
.collaborative(false)
.description("New playlist description")
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

