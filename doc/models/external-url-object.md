
# External Url Object

*This model accepts additional fields of type Object.*

## Structure

`ExternalUrlObject`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Spotify` | `String` | Optional | The [Spotify URL](https://developer.spotify.com/documentation/web-api/concepts/spotify-uris-ids) for the object. | String getSpotify() | setSpotify(String spotify) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.models.ExternalUrlObject;
import java.io.IOException;

ExternalUrlObject externalUrlObject = new ExternalUrlObject.Builder()
    .spotify("spotify0")
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

