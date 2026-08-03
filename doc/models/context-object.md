
# Context Object

*This model accepts additional fields of type Object.*

## Structure

`ContextObject`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Type` | `String` | Optional | The object type, e.g. "artist", "playlist", "album", "show". | String getType() | setType(String type) |
| `Href` | `String` | Optional | A link to the Web API endpoint providing full details of the track. | String getHref() | setHref(String href) |
| `ExternalUrls` | [`ExternalUrlObject`](../../doc/models/external-url-object.md) | Optional | - | ExternalUrlObject getExternalUrls() | setExternalUrls(ExternalUrlObject externalUrls) |
| `Uri` | `String` | Optional | The [Spotify URI](https://developer.spotify.com/documentation/web-api/concepts/spotify-uris-ids) for the context. | String getUri() | setUri(String uri) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.models.ContextObject;
import com.spotify.api.models.ExternalUrlObject;
import java.io.IOException;

ContextObject contextObject = new ContextObject.Builder()
    .type("type6")
    .href("href6")
    .externalUrls(new ExternalUrlObject.Builder()
        .spotify("spotify6")
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build())
    .uri("uri8")
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

