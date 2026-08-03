
# Episode Base

*This model accepts additional fields of type Object.*

## Structure

`EpisodeBase`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `AudioPreviewUrl` | `String` | Required | A URL to a 30 second preview (MP3 format) of the episode. `null` if not available. | String getAudioPreviewUrl() | setAudioPreviewUrl(String audioPreviewUrl) |
| `Description` | `String` | Required | A description of the episode. HTML tags are stripped away from this field, use `html_description` field in case HTML tags are needed. | String getDescription() | setDescription(String description) |
| `HtmlDescription` | `String` | Required | A description of the episode. This field may contain HTML tags. | String getHtmlDescription() | setHtmlDescription(String htmlDescription) |
| `DurationMs` | `int` | Required | The episode length in milliseconds. | int getDurationMs() | setDurationMs(int durationMs) |
| `Explicit` | `boolean` | Required | Whether or not the episode has explicit content (true = yes it does; false = no it does not OR unknown). | boolean getExplicit() | setExplicit(boolean explicit) |
| `ExternalUrls` | [`ExternalUrlObject`](../../doc/models/external-url-object.md) | Required | - | ExternalUrlObject getExternalUrls() | setExternalUrls(ExternalUrlObject externalUrls) |
| `Href` | `String` | Required | A link to the Web API endpoint providing full details of the episode. | String getHref() | setHref(String href) |
| `Id` | `String` | Required | The [Spotify ID](https://developer.spotify.com/documentation/web-api/concepts/spotify-uris-ids) for the episode. | String getId() | setId(String id) |
| `Images` | [`List<ImageObject>`](../../doc/models/image-object.md) | Required | The cover art for the episode in various sizes, widest first. | List<ImageObject> getImages() | setImages(List<ImageObject> images) |
| `IsExternallyHosted` | `boolean` | Required | True if the episode is hosted outside of Spotify's CDN. | boolean getIsExternallyHosted() | setIsExternallyHosted(boolean isExternallyHosted) |
| `IsPlayable` | `boolean` | Required | True if the episode is playable in the given market. Otherwise false. | boolean getIsPlayable() | setIsPlayable(boolean isPlayable) |
| `Language` | `String` | Optional | The language used in the episode, identified by a [ISO 639](https://en.wikipedia.org/wiki/ISO_639) code. This field is deprecated and might be removed in the future. Please use the `languages` field instead. | String getLanguage() | setLanguage(String language) |
| `Languages` | `List<String>` | Required | A list of the languages used in the episode, identified by their [ISO 639-1](https://en.wikipedia.org/wiki/ISO_639) code. | List<String> getLanguages() | setLanguages(List<String> languages) |
| `Name` | `String` | Required | The name of the episode. | String getName() | setName(String name) |
| `ReleaseDate` | `String` | Required | The date the episode was first released, for example `"1981-12-15"`. Depending on the precision, it might be shown as `"1981"` or `"1981-12"`. | String getReleaseDate() | setReleaseDate(String releaseDate) |
| `ReleaseDatePrecision` | [`ReleaseDatePrecision`](../../doc/models/release-date-precision.md) | Required | - | ReleaseDatePrecision getReleaseDatePrecision() | setReleaseDatePrecision(ReleaseDatePrecision releaseDatePrecision) |
| `ResumePoint` | [`ResumePointObject`](../../doc/models/resume-point-object.md) | Optional | - | ResumePointObject getResumePoint() | setResumePoint(ResumePointObject resumePoint) |
| `Type` | [`Type5`](../../doc/models/type-5.md) | Required | - | Type5 getType() | setType(Type5 type) |
| `Uri` | `String` | Required | The [Spotify URI](https://developer.spotify.com/documentation/web-api/concepts/spotify-uris-ids) for the episode. | String getUri() | setUri(String uri) |
| `Restrictions` | [`TrackRestrictionObject`](../../doc/models/track-restriction-object.md) | Optional | - | TrackRestrictionObject getRestrictions() | setRestrictions(TrackRestrictionObject restrictions) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.models.EpisodeBase;
import com.spotify.api.models.ExternalUrlObject;
import com.spotify.api.models.ImageObject;
import com.spotify.api.models.ReleaseDatePrecision;
import com.spotify.api.models.ResumePointObject;
import com.spotify.api.models.TrackRestrictionObject;
import com.spotify.api.models.Type5;
import java.io.IOException;
import java.util.Arrays;

EpisodeBase episodeBase = new EpisodeBase.Builder(
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
    ReleaseDatePrecision.YEAR,
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
.build();
```

