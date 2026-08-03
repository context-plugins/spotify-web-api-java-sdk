
# Paging Simplified Episode Object

*This model accepts additional fields of type Object.*

## Structure

`PagingSimplifiedEpisodeObject`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Href` | `String` | Required | A link to the Web API endpoint returning the full result of the request | String getHref() | setHref(String href) |
| `Limit` | `int` | Required | The maximum number of items in the response (as set in the query or by default). | int getLimit() | setLimit(int limit) |
| `Next` | `String` | Required | URL to the next page of items. ( `null` if none) | String getNext() | setNext(String next) |
| `Offset` | `int` | Required | The offset of the items returned (as set in the query or by default) | int getOffset() | setOffset(int offset) |
| `Previous` | `String` | Required | URL to the previous page of items. ( `null` if none) | String getPrevious() | setPrevious(String previous) |
| `Total` | `int` | Required | The total number of items available to return. | int getTotal() | setTotal(int total) |
| `Items` | [`List<EpisodeBase>`](../../doc/models/episode-base.md) | Required | - | List<EpisodeBase> getItems() | setItems(List<EpisodeBase> items) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.models.EpisodeBase;
import com.spotify.api.models.ExternalUrlObject;
import com.spotify.api.models.ImageObject;
import com.spotify.api.models.PagingSimplifiedEpisodeObject;
import com.spotify.api.models.ReleaseDatePrecision;
import com.spotify.api.models.ResumePointObject;
import com.spotify.api.models.TrackRestrictionObject;
import com.spotify.api.models.Type5;
import java.io.IOException;
import java.util.Arrays;

PagingSimplifiedEpisodeObject pagingSimplifiedEpisodeObject = new PagingSimplifiedEpisodeObject.Builder(
    "https://api.spotify.com/v1/me/shows?offset=0&limit=20\n",
    20,
    "https://api.spotify.com/v1/me/shows?offset=1&limit=1",
    0,
    "https://api.spotify.com/v1/me/shows?offset=1&limit=1",
    4,
    Arrays.asList(
        new EpisodeBase.Builder(
            "https://p.scdn.co/mp3-preview/2f37da1d4221f40b9d1a98cd191f4d6f1646ad17",
            "A Spotify podcast sharing fresh insights on important topics of the moment—in a way only Spotify can. You’ll hear from experts in the music, podcast and tech industries as we discover and uncover stories about our work and the world around us.\n",
            "<p>A Spotify podcast sharing fresh insights on important topics of the moment—in a way only Spotify can. You’ll hear from experts in the music, podcast and tech industries as we discover and uncover stories about our work and the world around us.</p>\n",
            1686230,
            false,
            new ExternalUrlObject.Builder()
                .spotify("spotify6")
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build(),
            "https://api.spotify.com/v1/episodes/5Xt5DXGzch68nYYamXrNxZ",
            "5Xt5DXGzch68nYYamXrNxZ",
            Arrays.asList(
                new ImageObject.Builder(
                    "https://i.scdn.co/image/ab67616d00001e02ff9ca10b55ce82ae553c8228\n",
                    300,
                    300
                )
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build()
            ),
            false,
            false,
            Arrays.asList(
                "fr",
                "en"
            ),
            "Starting Your Own Podcast: Tips, Tricks, and Advice From Anchor Creators\n",
            "1981-12-15",
            ReleaseDatePrecision.MONTH,
            Type5.EPISODE,
            "spotify:episode:0zLhl3WsOCQHbe1BPTiHgr"
        )
        .language("en")
        .resumePoint(new ResumePointObject.Builder()
                .fullyPlayed(false)
                .resumePositionMs(254)
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build())
        .restrictions(new TrackRestrictionObject.Builder()
                .reason("reason0")
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build())
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build()
    )
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

