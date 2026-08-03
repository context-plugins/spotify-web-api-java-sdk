
# Currently Playing Object

*This model accepts additional fields of type Object.*

## Structure

`CurrentlyPlayingObject`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Context` | [`ContextObject`](../../doc/models/context-object.md) | Optional | - | ContextObject getContext() | setContext(ContextObject context) |
| `Timestamp` | `Long` | Optional | Unix Millisecond Timestamp when data was fetched | Long getTimestamp() | setTimestamp(Long timestamp) |
| `ProgressMs` | `Integer` | Optional | Progress into the currently playing track or episode. Can be `null`. | Integer getProgressMs() | setProgressMs(Integer progressMs) |
| `IsPlaying` | `Boolean` | Optional | If something is currently playing, return `true`. | Boolean getIsPlaying() | setIsPlaying(Boolean isPlaying) |
| `Item` | [`CurrentlyPlayingObjectItem`](../../doc/models/containers/currently-playing-object-item.md) | Optional | This is a container for one-of cases. | CurrentlyPlayingObjectItem getItem() | setItem(CurrentlyPlayingObjectItem item) |
| `CurrentlyPlayingType` | `String` | Optional | The object type of the currently playing item. Can be one of `track`, `episode`, `ad` or `unknown`. | String getCurrentlyPlayingType() | setCurrentlyPlayingType(String currentlyPlayingType) |
| `Actions` | [`DisallowsObject`](../../doc/models/disallows-object.md) | Optional | - | DisallowsObject getActions() | setActions(DisallowsObject actions) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.models.AlbumRestrictionObject;
import com.spotify.api.models.AlbumType;
import com.spotify.api.models.ArtistObject;
import com.spotify.api.models.ContextObject;
import com.spotify.api.models.CurrentlyPlayingObject;
import com.spotify.api.models.ExternalUrlObject;
import com.spotify.api.models.FollowersObject;
import com.spotify.api.models.ImageObject;
import com.spotify.api.models.Reason;
import com.spotify.api.models.ReleaseDatePrecision;
import com.spotify.api.models.SimplifiedAlbumObject;
import com.spotify.api.models.SimplifiedArtistObject;
import com.spotify.api.models.TrackObject;
import com.spotify.api.models.Type;
import com.spotify.api.models.Type2;
import com.spotify.api.models.containers.CurrentlyPlayingObjectItem;
import java.io.IOException;
import java.util.Arrays;

CurrentlyPlayingObject currentlyPlayingObject = new CurrentlyPlayingObject.Builder()
    .context(new ContextObject.Builder()
        .type("type8")
        .href("href4")
        .externalUrls(new ExternalUrlObject.Builder()
            .spotify("spotify6")
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build())
        .uri("uri6")
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build())
    .timestamp(254L)
    .progressMs(226)
    .isPlaying(false)
    .item(CurrentlyPlayingObjectItem.fromTrackObject(
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
                    .build()
            ))
            .availableMarkets(Arrays.asList(
                "available_markets6",
                "available_markets7"
            ))
            .discNumber(30)
            .durationMs(222)
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build()
    ))
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

