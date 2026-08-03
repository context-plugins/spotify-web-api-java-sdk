
# Saved Audiobook Object

*This model accepts additional fields of type Object.*

## Structure

`SavedAudiobookObject`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `AddedAt` | `LocalDateTime` | Optional | The date and time the audiobook was saved<br>Timestamps are returned in ISO 8601 format as Coordinated Universal Time (UTC) with a zero offset: YYYY-MM-DDTHH:MM:SSZ.<br>If the time is imprecise (for example, the date/time of an album release), an additional field indicates the precision; see for example, release_date in an album object. | LocalDateTime getAddedAt() | setAddedAt(LocalDateTime addedAt) |
| `Audiobook` | [`AudiobookObject`](../../doc/models/audiobook-object.md) | Optional | - | AudiobookObject getAudiobook() | setAudiobook(AudiobookObject audiobook) |
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
import com.spotify.api.models.PagingSimplifiedChapterObject;
import com.spotify.api.models.ReleaseDatePrecision;
import com.spotify.api.models.ResumePointObject;
import com.spotify.api.models.SavedAudiobookObject;
import com.spotify.api.models.Type5;
import com.spotify.api.models.Type9;
import java.io.IOException;
import java.util.Arrays;

SavedAudiobookObject savedAudiobookObject = new SavedAudiobookObject.Builder()
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
    .build();
```

