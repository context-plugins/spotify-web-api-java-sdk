
# Many Chapters

*This model accepts additional fields of type Object.*

## Structure

`ManyChapters`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Chapters` | [`List<ChapterObject>`](../../doc/models/chapter-object.md) | Required | - | List<ChapterObject> getChapters() | setChapters(List<ChapterObject> chapters) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.models.AudiobookBase;
import com.spotify.api.models.AuthorObject;
import com.spotify.api.models.ChapterObject;
import com.spotify.api.models.ChapterRestrictionObject;
import com.spotify.api.models.CopyrightObject;
import com.spotify.api.models.ExternalUrlObject;
import com.spotify.api.models.ImageObject;
import com.spotify.api.models.ManyChapters;
import com.spotify.api.models.NarratorObject;
import com.spotify.api.models.ReleaseDatePrecision;
import com.spotify.api.models.ResumePointObject;
import com.spotify.api.models.Type5;
import com.spotify.api.models.Type9;
import java.io.IOException;
import java.util.Arrays;

ManyChapters manyChapters = new ManyChapters.Builder(
    Arrays.asList(
        new ChapterObject.Builder(
            "https://p.scdn.co/mp3-preview/2f37da1d4221f40b9d1a98cd191f4d6f1646ad17",
            1,
            "We kept on ascending, with occasional periods of quick descent, but in the main always ascending. Suddenly, I became conscious of the fact that the driver was in the act of pulling up the horses in the courtyard of a vast ruined castle, from whose tall black windows came no ray of light, and whose broken battlements showed a jagged line against the moonlit sky.\n",
            "<p>We kept on ascending, with occasional periods of quick descent, but in the main always ascending. Suddenly, I became conscious of the fact that the driver was in the act of pulling up the horses in the courtyard of a vast ruined castle, from whose tall black windows came no ray of light, and whose broken battlements showed a jagged line against the moonlit sky.</p>\n",
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
            Arrays.asList(
                "fr",
                "en"
            ),
            "Starting Your Own Podcast: Tips, Tricks, and Advice From Anchor Creators\n",
            "1981-12-15",
            ReleaseDatePrecision.DAY,
            Type5.EPISODE,
            "spotify:episode:0zLhl3WsOCQHbe1BPTiHgr",
            new AudiobookBase.Builder(
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
                        "https://i.scdn.co/image/ab67616d00001e02ff9ca10b55ce82ae553c8228\n",
                        300,
                        300
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
                        .build()
                ),
                "publisher4",
                Type9.AUDIOBOOK,
                "uri2",
                186
            )
            .edition("Unabridged")
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build()
        )
        .availableMarkets(Arrays.asList(
                "available_markets6",
                "available_markets7"
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
.build();
```

