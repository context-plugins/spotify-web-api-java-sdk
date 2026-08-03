
# Many Artists

*This model accepts additional fields of type Object.*

## Structure

`ManyArtists`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Artists` | [`List<ArtistObject>`](../../doc/models/artist-object.md) | Required | - | List<ArtistObject> getArtists() | setArtists(List<ArtistObject> artists) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.models.ArtistObject;
import com.spotify.api.models.ExternalUrlObject;
import com.spotify.api.models.FollowersObject;
import com.spotify.api.models.ManyArtists;
import java.io.IOException;
import java.util.Arrays;

ManyArtists manyArtists = new ManyArtists.Builder(
    Arrays.asList(
        new ArtistObject.Builder()
            .externalUrls(new ExternalUrlObject.Builder()
                .spotify("spotify6")
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build())
            .followers(new FollowersObject.Builder()
                .href("href0")
                .total(82)
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build())
            .genres(Arrays.asList(
                "Prog rock",
                "Grunge"
            ))
            .href("href2")
            .id("id0")
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build()
    )
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

