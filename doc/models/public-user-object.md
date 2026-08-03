
# Public User Object

*This model accepts additional fields of type Object.*

## Structure

`PublicUserObject`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `DisplayName` | `String` | Optional | The name displayed on the user's profile. `null` if not available. | String getDisplayName() | setDisplayName(String displayName) |
| `ExternalUrls` | [`ExternalUrlObject`](../../doc/models/external-url-object.md) | Optional | - | ExternalUrlObject getExternalUrls() | setExternalUrls(ExternalUrlObject externalUrls) |
| `Followers` | [`FollowersObject`](../../doc/models/followers-object.md) | Optional | - | FollowersObject getFollowers() | setFollowers(FollowersObject followers) |
| `Href` | `String` | Optional | A link to the Web API endpoint for this user. | String getHref() | setHref(String href) |
| `Id` | `String` | Optional | The [Spotify user ID](https://developer.spotify.com/documentation/web-api/concepts/spotify-uris-ids) for this user. | String getId() | setId(String id) |
| `Images` | [`List<ImageObject>`](../../doc/models/image-object.md) | Optional | The user's profile image. | List<ImageObject> getImages() | setImages(List<ImageObject> images) |
| `Type` | [`Type4`](../../doc/models/type-4.md) | Optional | - | Type4 getType() | setType(Type4 type) |
| `Uri` | `String` | Optional | The [Spotify URI](https://developer.spotify.com/documentation/web-api/concepts/spotify-uris-ids) for this user. | String getUri() | setUri(String uri) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.models.ExternalUrlObject;
import com.spotify.api.models.FollowersObject;
import com.spotify.api.models.PublicUserObject;
import java.io.IOException;

PublicUserObject publicUserObject = new PublicUserObject.Builder()
    .displayName("display_name0")
    .externalUrls(new ExternalUrlObject.Builder()
        .spotify("spotify6")
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build())
    .followers(new FollowersObject.Builder()
        .href("href0")
        .total(82)
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build())
    .href("href2")
    .id("id0")
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

