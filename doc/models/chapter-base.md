
# Chapter Base

*This model accepts additional fields of type Object.*

## Structure

`ChapterBase`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `AudioPreviewUrl` | `String` | Required | A URL to a 30 second preview (MP3 format) of the chapter. `null` if not available. | String getAudioPreviewUrl() | setAudioPreviewUrl(String audioPreviewUrl) |
| `AvailableMarkets` | `List<String>` | Optional | A list of the countries in which the chapter can be played, identified by their [ISO 3166-1 alpha-2](http://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) code. | List<String> getAvailableMarkets() | setAvailableMarkets(List<String> availableMarkets) |
| `ChapterNumber` | `int` | Required | The number of the chapter | int getChapterNumber() | setChapterNumber(int chapterNumber) |
| `Description` | `String` | Required | A description of the chapter. HTML tags are stripped away from this field, use `html_description` field in case HTML tags are needed. | String getDescription() | setDescription(String description) |
| `HtmlDescription` | `String` | Required | A description of the chapter. This field may contain HTML tags. | String getHtmlDescription() | setHtmlDescription(String htmlDescription) |
| `DurationMs` | `int` | Required | The chapter length in milliseconds. | int getDurationMs() | setDurationMs(int durationMs) |
| `Explicit` | `boolean` | Required | Whether or not the chapter has explicit content (true = yes it does; false = no it does not OR unknown). | boolean getExplicit() | setExplicit(boolean explicit) |
| `ExternalUrls` | [`ExternalUrlObject`](../../doc/models/external-url-object.md) | Required | - | ExternalUrlObject getExternalUrls() | setExternalUrls(ExternalUrlObject externalUrls) |
| `Href` | `String` | Required | A link to the Web API endpoint providing full details of the chapter. | String getHref() | setHref(String href) |
| `Id` | `String` | Required | The [Spotify ID](https://developer.spotify.com/documentation/web-api/concepts/spotify-uris-ids) for the chapter. | String getId() | setId(String id) |
| `Images` | [`List<ImageObject>`](../../doc/models/image-object.md) | Required | The cover art for the chapter in various sizes, widest first. | List<ImageObject> getImages() | setImages(List<ImageObject> images) |
| `IsPlayable` | `boolean` | Required | True if the chapter is playable in the given market. Otherwise false. | boolean getIsPlayable() | setIsPlayable(boolean isPlayable) |
| `Languages` | `List<String>` | Required | A list of the languages used in the chapter, identified by their [ISO 639-1](https://en.wikipedia.org/wiki/ISO_639) code. | List<String> getLanguages() | setLanguages(List<String> languages) |
| `Name` | `String` | Required | The name of the chapter. | String getName() | setName(String name) |
| `ReleaseDate` | `String` | Required | The date the chapter was first released, for example `"1981-12-15"`. Depending on the precision, it might be shown as `"1981"` or `"1981-12"`. | String getReleaseDate() | setReleaseDate(String releaseDate) |
| `ReleaseDatePrecision` | [`ReleaseDatePrecision`](../../doc/models/release-date-precision.md) | Required | - | ReleaseDatePrecision getReleaseDatePrecision() | setReleaseDatePrecision(ReleaseDatePrecision releaseDatePrecision) |
| `ResumePoint` | [`ResumePointObject`](../../doc/models/resume-point-object.md) | Optional | - | ResumePointObject getResumePoint() | setResumePoint(ResumePointObject resumePoint) |
| `Type` | [`Type5`](../../doc/models/type-5.md) | Required | - | Type5 getType() | setType(Type5 type) |
| `Uri` | `String` | Required | The [Spotify URI](https://developer.spotify.com/documentation/web-api/concepts/spotify-uris-ids) for the chapter. | String getUri() | setUri(String uri) |
| `Restrictions` | [`ChapterRestrictionObject`](../../doc/models/chapter-restriction-object.md) | Optional | - | ChapterRestrictionObject getRestrictions() | setRestrictions(ChapterRestrictionObject restrictions) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.models.ChapterBase;
import com.spotify.api.models.ChapterRestrictionObject;
import com.spotify.api.models.ExternalUrlObject;
import com.spotify.api.models.ImageObject;
import com.spotify.api.models.ReleaseDatePrecision;
import com.spotify.api.models.ResumePointObject;
import com.spotify.api.models.Type5;
import java.io.IOException;
import java.util.Arrays;

ChapterBase chapterBase = new ChapterBase.Builder(
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
    ReleaseDatePrecision.YEAR,
    Type5.EPISODE,
    "spotify:episode:0zLhl3WsOCQHbe1BPTiHgr"
)
.availableMarkets(Arrays.asList(
        "available_markets0",
        "available_markets1",
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
.build();
```

