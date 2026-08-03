
# Paging Simplified Album Object

*This model accepts additional fields of type Object.*

## Structure

`PagingSimplifiedAlbumObject`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Href` | `String` | Required | A link to the Web API endpoint returning the full result of the request | String getHref() | setHref(String href) |
| `Limit` | `int` | Required | The maximum number of items in the response (as set in the query or by default). | int getLimit() | setLimit(int limit) |
| `Next` | `String` | Required | URL to the next page of items. ( `null` if none) | String getNext() | setNext(String next) |
| `Offset` | `int` | Required | The offset of the items returned (as set in the query or by default) | int getOffset() | setOffset(int offset) |
| `Previous` | `String` | Required | URL to the previous page of items. ( `null` if none) | String getPrevious() | setPrevious(String previous) |
| `Total` | `int` | Required | The total number of items available to return. | int getTotal() | setTotal(int total) |
| `Items` | [`List<SimplifiedAlbumObject>`](../../doc/models/simplified-album-object.md) | Required | - | List<SimplifiedAlbumObject> getItems() | setItems(List<SimplifiedAlbumObject> items) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.models.AlbumRestrictionObject;
import com.spotify.api.models.AlbumType;
import com.spotify.api.models.ExternalUrlObject;
import com.spotify.api.models.ImageObject;
import com.spotify.api.models.PagingSimplifiedAlbumObject;
import com.spotify.api.models.Reason;
import com.spotify.api.models.ReleaseDatePrecision;
import com.spotify.api.models.SimplifiedAlbumObject;
import com.spotify.api.models.SimplifiedArtistObject;
import com.spotify.api.models.Type;
import com.spotify.api.models.Type2;
import java.io.IOException;
import java.util.Arrays;

PagingSimplifiedAlbumObject pagingSimplifiedAlbumObject = new PagingSimplifiedAlbumObject.Builder(
    "https://api.spotify.com/v1/me/shows?offset=0&limit=20\n",
    20,
    "https://api.spotify.com/v1/me/shows?offset=1&limit=1",
    0,
    "https://api.spotify.com/v1/me/shows?offset=1&limit=1",
    4,
    Arrays.asList(
        new SimplifiedAlbumObject.Builder(
            AlbumType.ALBUM,
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
            ReleaseDatePrecision.MONTH,
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
            )
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

