
# Saved Album Object

*This model accepts additional fields of type Object.*

## Structure

`SavedAlbumObject`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `AddedAt` | `LocalDateTime` | Optional | The date and time the album was saved<br>Timestamps are returned in ISO 8601 format as Coordinated Universal Time (UTC) with a zero offset: YYYY-MM-DDTHH:MM:SSZ.<br>If the time is imprecise (for example, the date/time of an album release), an additional field indicates the precision; see for example, release_date in an album object. | LocalDateTime getAddedAt() | setAddedAt(LocalDateTime addedAt) |
| `Album` | [`AlbumObject`](../../doc/models/album-object.md) | Optional | - | AlbumObject getAlbum() | setAlbum(AlbumObject album) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.DateTimeHelper;
import com.spotify.api.models.AlbumObject;
import com.spotify.api.models.AlbumRestrictionObject;
import com.spotify.api.models.AlbumType;
import com.spotify.api.models.CopyrightObject;
import com.spotify.api.models.ExternalIdObject;
import com.spotify.api.models.ExternalUrlObject;
import com.spotify.api.models.ImageObject;
import com.spotify.api.models.PagingSimplifiedTrackObject;
import com.spotify.api.models.Reason;
import com.spotify.api.models.ReleaseDatePrecision;
import com.spotify.api.models.SavedAlbumObject;
import com.spotify.api.models.SimplifiedArtistObject;
import com.spotify.api.models.SimplifiedTrackObject;
import com.spotify.api.models.Type;
import com.spotify.api.models.Type2;
import java.io.IOException;
import java.util.Arrays;

SavedAlbumObject savedAlbumObject = new SavedAlbumObject.Builder()
    .addedAt(DateTimeHelper.fromRfc8601DateTime("2016-03-13T12:52:32.123Z"))
    .album(new AlbumObject.Builder(
        AlbumType.SINGLE,
        170,
        Arrays.asList(
            "available_markets2",
            "available_markets3"
        ),
        new ExternalUrlObject.Builder()
            .spotify("spotify6")
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build(),
        "href0",
        "id8",
        Arrays.asList(
            new ImageObject.Builder(
                "url6",
                182,
                222
            )
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build()
        ),
        "name8",
        "release_date6",
        ReleaseDatePrecision.DAY,
        Type2.ALBUM,
        "uri2",
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
                .build(),
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
            "href6",
            142,
            "next8",
            238,
            "previous2",
            236,
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
                .build(),
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
            "genres5",
            "genres6",
            "genres7"
        ),
        "label8",
        78
    )
    .restrictions(new AlbumRestrictionObject.Builder()
            .reason(Reason.EXPLICIT)
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build())
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build())
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

