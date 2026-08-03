
# Simplified Artist Object

*This model accepts additional fields of type Object.*

## Structure

`SimplifiedArtistObject`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `ExternalUrls` | [`ExternalUrlObject`](../../doc/models/external-url-object.md) | Optional | - | ExternalUrlObject getExternalUrls() | setExternalUrls(ExternalUrlObject externalUrls) |
| `Href` | `String` | Optional | A link to the Web API endpoint providing full details of the artist. | String getHref() | setHref(String href) |
| `Id` | `String` | Optional | The [Spotify ID](https://developer.spotify.com/documentation/web-api/concepts/spotify-uris-ids) for the artist. | String getId() | setId(String id) |
| `Name` | `String` | Optional | The name of the artist. | String getName() | setName(String name) |
| `Type` | [`Type`](../../doc/models/type.md) | Optional | - | Type getType() | setType(Type type) |
| `Uri` | `String` | Optional | The [Spotify URI](https://developer.spotify.com/documentation/web-api/concepts/spotify-uris-ids) for the artist. | String getUri() | setUri(String uri) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.models.ExternalUrlObject;
import com.spotify.api.models.SimplifiedArtistObject;
import com.spotify.api.models.Type;
import java.io.IOException;

SimplifiedArtistObject simplifiedArtistObject = new SimplifiedArtistObject.Builder()
    .externalUrls(new ExternalUrlObject.Builder()
        .spotify("spotify6")
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build())
    .href("href6")
    .id("id4")
    .name("name4")
    .type(Type.ARTIST)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

