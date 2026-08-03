
# Playlist Owner Object

*This model accepts additional fields of type Object.*

## Structure

`PlaylistOwnerObject`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `ExternalUrls` | [`ExternalUrlObject`](../../doc/models/external-url-object.md) | Optional | - | ExternalUrlObject getExternalUrls() | setExternalUrls(ExternalUrlObject externalUrls) |
| `Followers` | [`FollowersObject`](../../doc/models/followers-object.md) | Optional | - | FollowersObject getFollowers() | setFollowers(FollowersObject followers) |
| `Href` | `String` | Optional | A link to the Web API endpoint for this user. | String getHref() | setHref(String href) |
| `Id` | `String` | Optional | The [Spotify user ID](https://developer.spotify.com/documentation/web-api/concepts/spotify-uris-ids) for this user. | String getId() | setId(String id) |
| `Type` | [`Type4`](../../doc/models/type-4.md) | Optional | - | Type4 getType() | setType(Type4 type) |
| `Uri` | `String` | Optional | The [Spotify URI](https://developer.spotify.com/documentation/web-api/concepts/spotify-uris-ids) for this user. | String getUri() | setUri(String uri) |
| `DisplayName` | `String` | Optional | The name displayed on the user's profile. `null` if not available. | String getDisplayName() | setDisplayName(String displayName) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.models.ExternalUrlObject;
import com.spotify.api.models.FollowersObject;
import com.spotify.api.models.PlaylistOwnerObject;
import com.spotify.api.models.Type4;
import java.io.IOException;

PlaylistOwnerObject playlistOwnerObject = new PlaylistOwnerObject.Builder()
    .externalUrls(new ExternalUrlObject.Builder()
        .spotify("spotify6")
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build())
    .followers(new FollowersObject.Builder()
        .href("href0")
        .total(82)
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build())
    .href("href6")
    .id("id4")
    .type(Type4.USER)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

