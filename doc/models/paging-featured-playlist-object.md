
# Paging Featured Playlist Object

*This model accepts additional fields of type Object.*

## Structure

`PagingFeaturedPlaylistObject`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Message` | `String` | Optional | The localized message of a playlist. | String getMessage() | setMessage(String message) |
| `Playlists` | [`PagingPlaylistObject`](../../doc/models/paging-playlist-object.md) | Optional | - | PagingPlaylistObject getPlaylists() | setPlaylists(PagingPlaylistObject playlists) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.models.ExternalUrlObject;
import com.spotify.api.models.PagingFeaturedPlaylistObject;
import com.spotify.api.models.PagingPlaylistObject;
import com.spotify.api.models.SimplifiedPlaylistObject;
import java.io.IOException;
import java.util.Arrays;

PagingFeaturedPlaylistObject pagingFeaturedPlaylistObject = new PagingFeaturedPlaylistObject.Builder()
    .message("Popular Playlists")
    .playlists(new PagingPlaylistObject.Builder(
        "href2",
        68,
        "next2",
        164,
        "previous8",
        162,
        Arrays.asList(
            new SimplifiedPlaylistObject.Builder()
                .collaborative(false)
                .description("description2")
                .externalUrls(new ExternalUrlObject.Builder()
                    .spotify("spotify6")
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                    .build())
                .href("href0")
                .id("id8")
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build(),
            new SimplifiedPlaylistObject.Builder()
                .collaborative(false)
                .description("description2")
                .externalUrls(new ExternalUrlObject.Builder()
                    .spotify("spotify6")
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                    .build())
                .href("href0")
                .id("id8")
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build(),
            new SimplifiedPlaylistObject.Builder()
                .collaborative(false)
                .description("description2")
                .externalUrls(new ExternalUrlObject.Builder()
                    .spotify("spotify6")
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                    .build())
                .href("href0")
                .id("id8")
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build()
        )
    )
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build())
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

