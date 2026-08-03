
# Private User Object

*This model accepts additional fields of type Object.*

## Structure

`PrivateUserObject`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Country` | `String` | Optional | The country of the user, as set in the user's account profile. An [ISO 3166-1 alpha-2 country code](http://en.wikipedia.org/wiki/ISO_3166-1_alpha-2). _This field is only available when the current user has granted access to the [user-read-private](https://developer.spotify.com/documentation/web-api/concepts/scopes/#list-of-scopes) scope._ | String getCountry() | setCountry(String country) |
| `DisplayName` | `String` | Optional | The name displayed on the user's profile. `null` if not available. | String getDisplayName() | setDisplayName(String displayName) |
| `Email` | `String` | Optional | The user's email address, as entered by the user when creating their account. _**Important!** This email address is unverified; there is no proof that it actually belongs to the user._ _This field is only available when the current user has granted access to the [user-read-email](https://developer.spotify.com/documentation/web-api/concepts/scopes/#list-of-scopes) scope._ | String getEmail() | setEmail(String email) |
| `ExplicitContent` | [`ExplicitContentSettingsObject`](../../doc/models/explicit-content-settings-object.md) | Optional | - | ExplicitContentSettingsObject getExplicitContent() | setExplicitContent(ExplicitContentSettingsObject explicitContent) |
| `ExternalUrls` | [`ExternalUrlObject`](../../doc/models/external-url-object.md) | Optional | - | ExternalUrlObject getExternalUrls() | setExternalUrls(ExternalUrlObject externalUrls) |
| `Followers` | [`FollowersObject`](../../doc/models/followers-object.md) | Optional | - | FollowersObject getFollowers() | setFollowers(FollowersObject followers) |
| `Href` | `String` | Optional | A link to the Web API endpoint for this user. | String getHref() | setHref(String href) |
| `Id` | `String` | Optional | The [Spotify user ID](https://developer.spotify.com/documentation/web-api/concepts/spotify-uris-ids) for the user. | String getId() | setId(String id) |
| `Images` | [`List<ImageObject>`](../../doc/models/image-object.md) | Optional | The user's profile image. | List<ImageObject> getImages() | setImages(List<ImageObject> images) |
| `Product` | `String` | Optional | The user's Spotify subscription level: "premium", "free", etc. (The subscription level "open" can be considered the same as "free".) _This field is only available when the current user has granted access to the [user-read-private](https://developer.spotify.com/documentation/web-api/concepts/scopes/#list-of-scopes) scope._ | String getProduct() | setProduct(String product) |
| `Type` | `String` | Optional | The object type: "user" | String getType() | setType(String type) |
| `Uri` | `String` | Optional | The [Spotify URI](https://developer.spotify.com/documentation/web-api/concepts/spotify-uris-ids) for the user. | String getUri() | setUri(String uri) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.models.ExplicitContentSettingsObject;
import com.spotify.api.models.ExternalUrlObject;
import com.spotify.api.models.PrivateUserObject;
import java.io.IOException;

PrivateUserObject privateUserObject = new PrivateUserObject.Builder()
    .country("country4")
    .displayName("display_name0")
    .email("email6")
    .explicitContent(new ExplicitContentSettingsObject.Builder()
        .filterEnabled(false)
        .filterLocked(false)
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build())
    .externalUrls(new ExternalUrlObject.Builder()
        .spotify("spotify6")
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build())
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

