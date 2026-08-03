
# Many Albums

*This model accepts additional fields of type Object.*

## Structure

`ManyAlbums`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Albums` | [`List<AlbumObject>`](../../doc/models/album-object.md) | Required | - | List<AlbumObject> getAlbums() | setAlbums(List<AlbumObject> albums) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.models.AlbumObject;
import com.spotify.api.models.AlbumRestrictionObject;
import com.spotify.api.models.AlbumType;
import com.spotify.api.models.CopyrightObject;
import com.spotify.api.models.ExternalIdObject;
import com.spotify.api.models.ExternalUrlObject;
import com.spotify.api.models.ImageObject;
import com.spotify.api.models.ManyAlbums;
import com.spotify.api.models.PagingSimplifiedTrackObject;
import com.spotify.api.models.Reason;
import com.spotify.api.models.ReleaseDatePrecision;
import com.spotify.api.models.SimplifiedArtistObject;
import com.spotify.api.models.SimplifiedTrackObject;
import com.spotify.api.models.Type;
import com.spotify.api.models.Type2;
import java.io.IOException;
import java.util.Arrays;

ManyAlbums manyAlbums = new ManyAlbums.Builder(
    Arrays.asList(
        new AlbumObject.Builder(
            AlbumType.SINGLE,
            9,
            Arrays.asList(
                "CA",
                "BR",
                "IT"
            ),
            new ExternalUrlObject.Builder()
                .spotify("spotify6")
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build(),
            "href0",
            "2up3OPMp9Tb4dAKM2erWXQ",
            Arrays.asList(
                new ImageObject.Builder(
                    "https://i.scdn.co/image/ab67616d00001e02ff9ca10b55ce82ae553c8228\n",
                    300,
                    300
                )
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build()
            ),
            "name8",
            "1981-12",
            ReleaseDatePrecision.DAY,
            Type2.ALBUM,
            "spotify:album:2up3OPMp9Tb4dAKM2erWXQ",
            Arrays.asList(
                new SimplifiedArtistObject.Builder()
                    .externalUrls(new ExternalUrlObject.Builder()
                        .spotify("spotify6")
                    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                        .build())
                    .href("href2")
                    .id("id0")
                    .name("name0")
                    .type(Type.ARTIST)
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                    .build()
            ),
            new PagingSimplifiedTrackObject.Builder(
                "https://api.spotify.com/v1/me/shows?offset=0&limit=20\n",
                20,
                "https://api.spotify.com/v1/me/shows?offset=1&limit=1",
                0,
                "https://api.spotify.com/v1/me/shows?offset=1&limit=1",
                4,
                Arrays.asList(
                    new SimplifiedTrackObject.Builder()
                        .artists(Arrays.asList(
                            new SimplifiedArtistObject.Builder()
                                .externalUrls(new ExternalUrlObject.Builder()
                                    .spotify("spotify6")
                                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                                    .build())
                                .href("href2")
                                .id("id0")
                                .name("name0")
                                .type(Type.ARTIST)
                            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                                .build()
                        ))
                        .availableMarkets(Arrays.asList(
                            "available_markets2"
                        ))
                        .discNumber(244)
                        .durationMs(52)
                        .explicit(false)
                    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                        .build()
                )
            )
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build(),
            Arrays.asList(
                new CopyrightObject.Builder()
                    .text("text2")
                    .type("type2")
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                    .build()
            ),
            new ExternalIdObject.Builder()
                .isrc("isrc8")
                .ean("ean8")
                .upc("upc2")
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build(),
            Arrays.asList(
                "Egg punk",
                "Noise rock"
            ),
            "label8",
            66
        )
        .restrictions(new AlbumRestrictionObject.Builder()
                .reason(Reason.EXPLICIT)
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build())
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build()
    )
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

