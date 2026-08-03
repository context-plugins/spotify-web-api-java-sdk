
# Show Object

*This model accepts additional fields of type Object.*

## Structure

`ShowObject`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `AvailableMarkets` | `List<String>` | Required | A list of the countries in which the show can be played, identified by their [ISO 3166-1 alpha-2](http://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) code. | List<String> getAvailableMarkets() | setAvailableMarkets(List<String> availableMarkets) |
| `Copyrights` | [`List<CopyrightObject>`](../../doc/models/copyright-object.md) | Required | The copyright statements of the show. | List<CopyrightObject> getCopyrights() | setCopyrights(List<CopyrightObject> copyrights) |
| `Description` | `String` | Required | A description of the show. HTML tags are stripped away from this field, use `html_description` field in case HTML tags are needed. | String getDescription() | setDescription(String description) |
| `HtmlDescription` | `String` | Required | A description of the show. This field may contain HTML tags. | String getHtmlDescription() | setHtmlDescription(String htmlDescription) |
| `Explicit` | `boolean` | Required | Whether or not the show has explicit content (true = yes it does; false = no it does not OR unknown). | boolean getExplicit() | setExplicit(boolean explicit) |
| `ExternalUrls` | [`ExternalUrlObject`](../../doc/models/external-url-object.md) | Required | - | ExternalUrlObject getExternalUrls() | setExternalUrls(ExternalUrlObject externalUrls) |
| `Href` | `String` | Required | A link to the Web API endpoint providing full details of the show. | String getHref() | setHref(String href) |
| `Id` | `String` | Required | The [Spotify ID](https://developer.spotify.com/documentation/web-api/concepts/spotify-uris-ids) for the show. | String getId() | setId(String id) |
| `Images` | [`List<ImageObject>`](../../doc/models/image-object.md) | Required | The cover art for the show in various sizes, widest first. | List<ImageObject> getImages() | setImages(List<ImageObject> images) |
| `IsExternallyHosted` | `boolean` | Required | True if all of the shows episodes are hosted outside of Spotify's CDN. This field might be `null` in some cases. | boolean getIsExternallyHosted() | setIsExternallyHosted(boolean isExternallyHosted) |
| `Languages` | `List<String>` | Required | A list of the languages used in the show, identified by their [ISO 639](https://en.wikipedia.org/wiki/ISO_639) code. | List<String> getLanguages() | setLanguages(List<String> languages) |
| `MediaType` | `String` | Required | The media type of the show. | String getMediaType() | setMediaType(String mediaType) |
| `Name` | `String` | Required | The name of the episode. | String getName() | setName(String name) |
| `Publisher` | `String` | Required | The publisher of the show. | String getPublisher() | setPublisher(String publisher) |
| `Type` | [`Type6`](../../doc/models/type-6.md) | Required | - | Type6 getType() | setType(Type6 type) |
| `Uri` | `String` | Required | The [Spotify URI](https://developer.spotify.com/documentation/web-api/concepts/spotify-uris-ids) for the show. | String getUri() | setUri(String uri) |
| `TotalEpisodes` | `int` | Required | The total number of episodes in the show. | int getTotalEpisodes() | setTotalEpisodes(int totalEpisodes) |
| `Episodes` | [`PagingSimplifiedEpisodeObject`](../../doc/models/paging-simplified-episode-object.md) | Required | - | PagingSimplifiedEpisodeObject getEpisodes() | setEpisodes(PagingSimplifiedEpisodeObject episodes) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.models.CopyrightObject;
import com.spotify.api.models.EpisodeBase;
import com.spotify.api.models.ExternalUrlObject;
import com.spotify.api.models.ImageObject;
import com.spotify.api.models.PagingSimplifiedEpisodeObject;
import com.spotify.api.models.ReleaseDatePrecision;
import com.spotify.api.models.ResumePointObject;
import com.spotify.api.models.ShowObject;
import com.spotify.api.models.TrackRestrictionObject;
import com.spotify.api.models.Type5;
import com.spotify.api.models.Type6;
import java.io.IOException;
import java.util.Arrays;

ShowObject showObject = new ShowObject.Builder(
    Arrays.asList(
        "available_markets2"
    ),
    Arrays.asList(
        new CopyrightObject.Builder()
            .text("text2")
            .type("type2")
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build()
    ),
    "description8",
    "html_description8",
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
    false,
    Arrays.asList(
        "languages5"
    ),
    "media_type6",
    "name8",
    "publisher6",
    Type6.SHOW,
    "uri2",
    230,
    new PagingSimplifiedEpisodeObject.Builder(
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
    .build()
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

