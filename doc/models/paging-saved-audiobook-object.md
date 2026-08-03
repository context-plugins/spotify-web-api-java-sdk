
# Paging Saved Audiobook Object

*This model accepts additional fields of type Object.*

## Structure

`PagingSavedAudiobookObject`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Href` | `String` | Required | A link to the Web API endpoint returning the full result of the request | String getHref() | setHref(String href) |
| `Limit` | `int` | Required | The maximum number of items in the response (as set in the query or by default). | int getLimit() | setLimit(int limit) |
| `Next` | `String` | Required | URL to the next page of items. ( `null` if none) | String getNext() | setNext(String next) |
| `Offset` | `int` | Required | The offset of the items returned (as set in the query or by default) | int getOffset() | setOffset(int offset) |
| `Previous` | `String` | Required | URL to the previous page of items. ( `null` if none) | String getPrevious() | setPrevious(String previous) |
| `Total` | `int` | Required | The total number of items available to return. | int getTotal() | setTotal(int total) |
| `Items` | [`List<SavedAudiobookObject>`](../../doc/models/saved-audiobook-object.md) | Required | - | List<SavedAudiobookObject> getItems() | setItems(List<SavedAudiobookObject> items) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.DateTimeHelper;
import com.spotify.api.models.AudiobookObject;
import com.spotify.api.models.AuthorObject;
import com.spotify.api.models.ChapterBase;
import com.spotify.api.models.ChapterRestrictionObject;
import com.spotify.api.models.CopyrightObject;
import com.spotify.api.models.ExternalUrlObject;
import com.spotify.api.models.ImageObject;
import com.spotify.api.models.NarratorObject;
import com.spotify.api.models.PagingSavedAudiobookObject;
import com.spotify.api.models.PagingSimplifiedChapterObject;
import com.spotify.api.models.ReleaseDatePrecision;
import com.spotify.api.models.ResumePointObject;
import com.spotify.api.models.SavedAudiobookObject;
import com.spotify.api.models.Type5;
import com.spotify.api.models.Type9;
import java.io.IOException;
import java.util.Arrays;

PagingSavedAudiobookObject pagingSavedAudiobookObject = new PagingSavedAudiobookObject.Builder(
    "https://api.spotify.com/v1/me/shows?offset=0&limit=20\n",
    20,
    "https://api.spotify.com/v1/me/shows?offset=1&limit=1",
    0,
    "https://api.spotify.com/v1/me/shows?offset=1&limit=1",
    4,
    Arrays.asList(
        new SavedAudiobookObject.Builder()
            .addedAt(DateTimeHelper.fromRfc8601DateTime("2016-03-13T12:52:32.123Z"))
            .audiobook(new AudiobookObject.Builder(
                Arrays.asList(
                    new AuthorObject.Builder()
                        .name("name0")
                    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                        .build()
                ),
                Arrays.asList(
                    "available_markets2",
                    "available_markets3",
                    "available_markets4"
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
                "description2",
                "html_description2",
                false,
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
                Arrays.asList(
                    "languages3",
                    "languages4"
                ),
                "media_type4",
                "name8",
                Arrays.asList(
                    new NarratorObject.Builder()
                        .name("name0")
                    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                        .build(),
                    new NarratorObject.Builder()
                        .name("name0")
                    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                        .build()
                ),
                "publisher4",
                Type9.AUDIOBOOK,
                "uri2",
                186,
                new PagingSimplifiedChapterObject.Builder(
                    "href4",
                    230,
                    "next0",
                    122,
                    "previous0",
                    136,
                    Arrays.asList(
                        new ChapterBase.Builder(
                            "audio_preview_url4",
                            164,
                            "description2",
                            "html_description2",
                            52,
                            false,
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
                                "languages5"
                            ),
                            "name8",
                            "release_date6",
                            ReleaseDatePrecision.MONTH,
                            Type5.EPISODE,
                            "uri2"
                        )
                        .availableMarkets(Arrays.asList(
                                "available_markets2"
                            ))
                        .resumePoint(new ResumePointObject.Builder()
                                .fullyPlayed(false)
                                .resumePositionMs(254)
                            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                                .build())
                        .restrictions(new ChapterRestrictionObject.Builder()
                                .reason("reason0")
                            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                                .build())
                        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                        .build()
                    )
                )
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build()
            )
            .edition("edition8")
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build())
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build()
    )
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

