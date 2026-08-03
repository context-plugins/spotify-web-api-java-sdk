
# Paging Track Object

*This model accepts additional fields of type Object.*

## Structure

`PagingTrackObject`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Href` | `String` | Required | A link to the Web API endpoint returning the full result of the request | String getHref() | setHref(String href) |
| `Limit` | `int` | Required | The maximum number of items in the response (as set in the query or by default). | int getLimit() | setLimit(int limit) |
| `Next` | `String` | Required | URL to the next page of items. ( `null` if none) | String getNext() | setNext(String next) |
| `Offset` | `int` | Required | The offset of the items returned (as set in the query or by default) | int getOffset() | setOffset(int offset) |
| `Previous` | `String` | Required | URL to the previous page of items. ( `null` if none) | String getPrevious() | setPrevious(String previous) |
| `Total` | `int` | Required | The total number of items available to return. | int getTotal() | setTotal(int total) |
| `Items` | [`List<TrackObject>`](../../doc/models/track-object.md) | Required | - | List<TrackObject> getItems() | setItems(List<TrackObject> items) |
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
import com.spotify.api.models.PagingTrackObject;
import com.spotify.api.models.Reason;
import com.spotify.api.models.ReleaseDatePrecision;
import com.spotify.api.models.SimplifiedAlbumObject;
import com.spotify.api.models.SimplifiedArtistObject;
import com.spotify.api.models.TrackObject;
import com.spotify.api.models.Type;
import com.spotify.api.models.Type2;
import java.io.IOException;
import java.util.Arrays;

PagingTrackObject pagingTrackObject = new PagingTrackObject.Builder(
    "https://api.spotify.com/v1/me/shows?offset=0&limit=20\n",
    20,
    "https://api.spotify.com/v1/me/shows?offset=1&limit=1",
    0,
    "https://api.spotify.com/v1/me/shows?offset=1&limit=1",
    4,
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
                    .build()
            ))
            .availableMarkets(Arrays.asList(
                "available_markets2"
            ))
            .discNumber(244)
            .durationMs(52)
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build()
    )
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

