
# Many Episodes

*This model accepts additional fields of type Object.*

## Structure

`ManyEpisodes`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Episodes` | [`List<EpisodeObject>`](../../doc/models/episode-object.md) | Required | - | List<EpisodeObject> getEpisodes() | setEpisodes(List<EpisodeObject> episodes) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.models.CopyrightObject;
import com.spotify.api.models.EpisodeObject;
import com.spotify.api.models.ExternalUrlObject;
import com.spotify.api.models.ImageObject;
import com.spotify.api.models.ManyEpisodes;
import com.spotify.api.models.ReleaseDatePrecision;
import com.spotify.api.models.ResumePointObject;
import com.spotify.api.models.ShowBase;
import com.spotify.api.models.TrackRestrictionObject;
import com.spotify.api.models.Type5;
import com.spotify.api.models.Type6;
import java.io.IOException;
import java.util.Arrays;

ManyEpisodes manyEpisodes = new ManyEpisodes.Builder(
    Arrays.asList(
        new EpisodeObject.Builder(
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
            ReleaseDatePrecision.DAY,
            Type5.EPISODE,
            "spotify:episode:0zLhl3WsOCQHbe1BPTiHgr",
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
                        "https://i.scdn.co/image/ab67616d00001e02ff9ca10b55ce82ae553c8228\n",
                        300,
                        300
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

