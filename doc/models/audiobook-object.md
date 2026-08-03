
# Audiobook Object

*This model accepts additional fields of type Object.*

## Structure

`AudiobookObject`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Authors` | [`List<AuthorObject>`](../../doc/models/author-object.md) | Required | The author(s) for the audiobook. | List<AuthorObject> getAuthors() | setAuthors(List<AuthorObject> authors) |
| `AvailableMarkets` | `List<String>` | Required | A list of the countries in which the audiobook can be played, identified by their [ISO 3166-1 alpha-2](http://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) code. | List<String> getAvailableMarkets() | setAvailableMarkets(List<String> availableMarkets) |
| `Copyrights` | [`List<CopyrightObject>`](../../doc/models/copyright-object.md) | Required | The copyright statements of the audiobook. | List<CopyrightObject> getCopyrights() | setCopyrights(List<CopyrightObject> copyrights) |
| `Description` | `String` | Required | A description of the audiobook. HTML tags are stripped away from this field, use `html_description` field in case HTML tags are needed. | String getDescription() | setDescription(String description) |
| `HtmlDescription` | `String` | Required | A description of the audiobook. This field may contain HTML tags. | String getHtmlDescription() | setHtmlDescription(String htmlDescription) |
| `Edition` | `String` | Optional | The edition of the audiobook. | String getEdition() | setEdition(String edition) |
| `Explicit` | `boolean` | Required | Whether or not the audiobook has explicit content (true = yes it does; false = no it does not OR unknown). | boolean getExplicit() | setExplicit(boolean explicit) |
| `ExternalUrls` | [`ExternalUrlObject`](../../doc/models/external-url-object.md) | Required | - | ExternalUrlObject getExternalUrls() | setExternalUrls(ExternalUrlObject externalUrls) |
| `Href` | `String` | Required | A link to the Web API endpoint providing full details of the audiobook. | String getHref() | setHref(String href) |
| `Id` | `String` | Required | The [Spotify ID](https://developer.spotify.com/documentation/web-api/concepts/spotify-uris-ids) for the audiobook. | String getId() | setId(String id) |
| `Images` | [`List<ImageObject>`](../../doc/models/image-object.md) | Required | The cover art for the audiobook in various sizes, widest first. | List<ImageObject> getImages() | setImages(List<ImageObject> images) |
| `Languages` | `List<String>` | Required | A list of the languages used in the audiobook, identified by their [ISO 639](https://en.wikipedia.org/wiki/ISO_639) code. | List<String> getLanguages() | setLanguages(List<String> languages) |
| `MediaType` | `String` | Required | The media type of the audiobook. | String getMediaType() | setMediaType(String mediaType) |
| `Name` | `String` | Required | The name of the audiobook. | String getName() | setName(String name) |
| `Narrators` | [`List<NarratorObject>`](../../doc/models/narrator-object.md) | Required | The narrator(s) for the audiobook. | List<NarratorObject> getNarrators() | setNarrators(List<NarratorObject> narrators) |
| `Publisher` | `String` | Required | The publisher of the audiobook. | String getPublisher() | setPublisher(String publisher) |
| `Type` | [`Type9`](../../doc/models/type-9.md) | Required | - | Type9 getType() | setType(Type9 type) |
| `Uri` | `String` | Required | The [Spotify URI](https://developer.spotify.com/documentation/web-api/concepts/spotify-uris-ids) for the audiobook. | String getUri() | setUri(String uri) |
| `TotalChapters` | `int` | Required | The number of chapters in this audiobook. | int getTotalChapters() | setTotalChapters(int totalChapters) |
| `Chapters` | [`PagingSimplifiedChapterObject`](../../doc/models/paging-simplified-chapter-object.md) | Required | - | PagingSimplifiedChapterObject getChapters() | setChapters(PagingSimplifiedChapterObject chapters) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
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
import com.spotify.api.models.Type5;
import com.spotify.api.models.Type9;
import java.io.IOException;
import java.util.Arrays;

AudiobookObject audiobookObject = new AudiobookObject.Builder(
    Arrays.asList(
        new AuthorObject.Builder()
            .name("name0")
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build()
    ),
    Arrays.asList(
        "available_markets4",
        "available_markets5"
    ),
    Arrays.asList(
        new CopyrightObject.Builder()
            .text("text2")
            .type("type2")
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build()
    ),
    "description0",
    "html_description0",
    false,
    new ExternalUrlObject.Builder()
        .spotify("spotify6")
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build(),
    "href2",
    "id0",
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
        "languages1",
        "languages2",
        "languages3"
    ),
    "media_type2",
    "name0",
    Arrays.asList(
        new NarratorObject.Builder()
            .name("name0")
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build()
    ),
    "publisher2",
    Type9.AUDIOBOOK,
    "uri4",
    72,
    new PagingSimplifiedChapterObject.Builder(
        "https://api.spotify.com/v1/me/shows?offset=0&limit=20\n",
        20,
        "https://api.spotify.com/v1/me/shows?offset=1&limit=1",
        0,
        "https://api.spotify.com/v1/me/shows?offset=1&limit=1",
        4,
        Arrays.asList(
            new ChapterBase.Builder(
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
                ReleaseDatePrecision.MONTH,
                Type5.EPISODE,
                "spotify:episode:0zLhl3WsOCQHbe1BPTiHgr"
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
.edition("Unabridged")
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

