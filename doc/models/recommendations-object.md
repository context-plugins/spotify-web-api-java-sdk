
# Recommendations Object

*This model accepts additional fields of type Object.*

## Structure

`RecommendationsObject`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Seeds` | [`List<RecommendationSeedObject>`](../../doc/models/recommendation-seed-object.md) | Required | An array of recommendation seed objects. | List<RecommendationSeedObject> getSeeds() | setSeeds(List<RecommendationSeedObject> seeds) |
| `Tracks` | [`List<TrackObject>`](../../doc/models/track-object.md) | Required | An array of track objects ordered according to the parameters supplied. | List<TrackObject> getTracks() | setTracks(List<TrackObject> tracks) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.models.AlbumRestrictionObject;
import com.spotify.api.models.AlbumType;
import com.spotify.api.models.ArtistObject;
import com.spotify.api.models.ExternalUrlObject;
import com.spotify.api.models.FollowersObject;
import com.spotify.api.models.ImageObject;
import com.spotify.api.models.Reason;
import com.spotify.api.models.RecommendationSeedObject;
import com.spotify.api.models.RecommendationsObject;
import com.spotify.api.models.ReleaseDatePrecision;
import com.spotify.api.models.SimplifiedAlbumObject;
import com.spotify.api.models.SimplifiedArtistObject;
import com.spotify.api.models.TrackObject;
import com.spotify.api.models.Type;
import com.spotify.api.models.Type2;
import java.io.IOException;
import java.util.Arrays;

RecommendationsObject recommendationsObject = new RecommendationsObject.Builder(
    Arrays.asList(
        new RecommendationSeedObject.Builder()
            .afterFilteringSize(36)
            .afterRelinkingSize(144)
            .href("href4")
            .id("id2")
            .initialPoolSize(42)
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build()
    ),
    Arrays.asList(
        new TrackObject.Builder()
            .album(new SimplifiedAlbumObject.Builder(
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
                )
            )
            .restrictions(new AlbumRestrictionObject.Builder()
                    .reason(Reason.EXPLICIT)
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                    .build())
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build())
            .artists(Arrays.asList(
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
                        "genres7",
                        "genres8"
                    ))
                    .href("href2")
                    .id("id0")
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                    .build(),
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
                        "genres7",
                        "genres8"
                    ))
                    .href("href2")
                    .id("id0")
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                    .build(),
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
                        "genres7",
                        "genres8"
                    ))
                    .href("href2")
                    .id("id0")
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                    .build()
            ))
            .availableMarkets(Arrays.asList(
                "available_markets8",
                "available_markets9"
            ))
            .discNumber(168)
            .durationMs(232)
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build()
    )
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

