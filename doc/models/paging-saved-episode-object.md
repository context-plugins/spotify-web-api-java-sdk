
# Paging Saved Episode Object

*This model accepts additional fields of type Object.*

## Structure

`PagingSavedEpisodeObject`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Href` | `String` | Required | A link to the Web API endpoint returning the full result of the request | String getHref() | setHref(String href) |
| `Limit` | `int` | Required | The maximum number of items in the response (as set in the query or by default). | int getLimit() | setLimit(int limit) |
| `Next` | `String` | Required | URL to the next page of items. ( `null` if none) | String getNext() | setNext(String next) |
| `Offset` | `int` | Required | The offset of the items returned (as set in the query or by default) | int getOffset() | setOffset(int offset) |
| `Previous` | `String` | Required | URL to the previous page of items. ( `null` if none) | String getPrevious() | setPrevious(String previous) |
| `Total` | `int` | Required | The total number of items available to return. | int getTotal() | setTotal(int total) |
| `Items` | [`List<SavedEpisodeObject>`](../../doc/models/saved-episode-object.md) | Required | - | List<SavedEpisodeObject> getItems() | setItems(List<SavedEpisodeObject> items) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.DateTimeHelper;
import com.spotify.api.models.CopyrightObject;
import com.spotify.api.models.EpisodeObject;
import com.spotify.api.models.ExternalUrlObject;
import com.spotify.api.models.ImageObject;
import com.spotify.api.models.PagingSavedEpisodeObject;
import com.spotify.api.models.ReleaseDatePrecision;
import com.spotify.api.models.ResumePointObject;
import com.spotify.api.models.SavedEpisodeObject;
import com.spotify.api.models.ShowBase;
import com.spotify.api.models.TrackRestrictionObject;
import com.spotify.api.models.Type5;
import com.spotify.api.models.Type6;
import java.io.IOException;
import java.util.Arrays;

PagingSavedEpisodeObject pagingSavedEpisodeObject = new PagingSavedEpisodeObject.Builder(
    "https://api.spotify.com/v1/me/shows?offset=0&limit=20\n",
    20,
    "https://api.spotify.com/v1/me/shows?offset=1&limit=1",
    0,
    "https://api.spotify.com/v1/me/shows?offset=1&limit=1",
    4,
    Arrays.asList(
        new SavedEpisodeObject.Builder()
            .addedAt(DateTimeHelper.fromRfc8601DateTime("2016-03-13T12:52:32.123Z"))
            .episode(new EpisodeObject.Builder(
                "audio_preview_url8",
                "description2",
                "html_description8",
                46,
                false,
                new ExternalUrlObject.Builder()
                    .spotify("spotify6")
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                    .build(),
                "href4",
                "id2",
                Arrays.asList(
                    new ImageObject.Builder(
                        "url6",
                        182,
                        222
                    )
                    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                    .build(),
                    new ImageObject.Builder(
                        "url6",
                        182,
                        222
                    )
                    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                    .build(),
                    new ImageObject.Builder(
                        "url6",
                        182,
                        222
                    )
                    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                    .build()
                ),
                false,
                false,
                Arrays.asList(
                    "languages9",
                    "languages0",
                    "languages1"
                ),
                "name2",
                "release_date0",
                ReleaseDatePrecision.YEAR,
                Type5.EPISODE,
                "uri6",
                new ShowBase.Builder(
                    Arrays.asList(
                        "available_markets0",
                        "available_markets1",
                        "available_markets2"
                    ),
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
                            .build(),
                        new CopyrightObject.Builder()
                            .text("text2")
                            .type("type2")
                        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                            .build()
                    ),
                    "description4",
                    "html_description4",
                    false,
                    new ExternalUrlObject.Builder()
                        .spotify("spotify6")
                    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                        .build(),
                    "href8",
                    "id6",
                    Arrays.asList(
                        new ImageObject.Builder(
                            "url6",
                            182,
                            222
                        )
                        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                        .build(),
                        new ImageObject.Builder(
                            "url6",
                            182,
                            222
                        )
                        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                        .build(),
                        new ImageObject.Builder(
                            "url6",
                            182,
                            222
                        )
                        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                        .build()
                    ),
                    false,
                    Arrays.asList(
                        "languages7",
                        "languages6",
                        "languages5"
                    ),
                    "media_type6",
                    "name6",
                    "publisher6",
                    Type6.SHOW,
                    "uri0",
                    198
                )
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build()
            )
            .language("language4")
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
            .build())
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build()
    )
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

