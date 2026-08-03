
# Track Object

*This model accepts additional fields of type Object.*

## Structure

`TrackObject`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Album` | [`SimplifiedAlbumObject`](../../doc/models/simplified-album-object.md) | Optional | - | SimplifiedAlbumObject getAlbum() | setAlbum(SimplifiedAlbumObject album) |
| `Artists` | [`List<ArtistObject>`](../../doc/models/artist-object.md) | Optional | The artists who performed the track. Each artist object includes a link in `href` to more detailed information about the artist. | List<ArtistObject> getArtists() | setArtists(List<ArtistObject> artists) |
| `AvailableMarkets` | `List<String>` | Optional | A list of the countries in which the track can be played, identified by their [ISO 3166-1 alpha-2](http://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) code. | List<String> getAvailableMarkets() | setAvailableMarkets(List<String> availableMarkets) |
| `DiscNumber` | `Integer` | Optional | The disc number (usually `1` unless the album consists of more than one disc). | Integer getDiscNumber() | setDiscNumber(Integer discNumber) |
| `DurationMs` | `Integer` | Optional | The track length in milliseconds. | Integer getDurationMs() | setDurationMs(Integer durationMs) |
| `Explicit` | `Boolean` | Optional | Whether or not the track has explicit lyrics ( `true` = yes it does; `false` = no it does not OR unknown). | Boolean getExplicit() | setExplicit(Boolean explicit) |
| `ExternalIds` | [`ExternalIdObject`](../../doc/models/external-id-object.md) | Optional | - | ExternalIdObject getExternalIds() | setExternalIds(ExternalIdObject externalIds) |
| `ExternalUrls` | [`ExternalUrlObject`](../../doc/models/external-url-object.md) | Optional | - | ExternalUrlObject getExternalUrls() | setExternalUrls(ExternalUrlObject externalUrls) |
| `Href` | `String` | Optional | A link to the Web API endpoint providing full details of the track. | String getHref() | setHref(String href) |
| `Id` | `String` | Optional | The [Spotify ID](https://developer.spotify.com/documentation/web-api/concepts/spotify-uris-ids) for the track. | String getId() | setId(String id) |
| `IsPlayable` | `Boolean` | Optional | Part of the response when [Track Relinking](https://developer.spotify.com/documentation/web-api/concepts/track-relinking) is applied. If `true`, the track is playable in the given market. Otherwise `false`. | Boolean getIsPlayable() | setIsPlayable(Boolean isPlayable) |
| `LinkedFrom` | [`LinkedTrackObject`](../../doc/models/linked-track-object.md) | Optional | - | LinkedTrackObject getLinkedFrom() | setLinkedFrom(LinkedTrackObject linkedFrom) |
| `Restrictions` | [`TrackRestrictionObject`](../../doc/models/track-restriction-object.md) | Optional | - | TrackRestrictionObject getRestrictions() | setRestrictions(TrackRestrictionObject restrictions) |
| `Name` | `String` | Optional | The name of the track. | String getName() | setName(String name) |
| `Popularity` | `Integer` | Optional | The popularity of the track. The value will be between 0 and 100, with 100 being the most popular.<br/>The popularity of a track is a value between 0 and 100, with 100 being the most popular. The popularity is calculated by algorithm and is based, in the most part, on the total number of plays the track has had and how recent those plays are.<br/>Generally speaking, songs that are being played a lot now will have a higher popularity than songs that were played a lot in the past. Duplicate tracks (e.g. the same track from a single and an album) are rated independently. Artist and album popularity is derived mathematically from track popularity. _**Note**: the popularity value may lag actual popularity by a few days: the value is not updated in real time._ | Integer getPopularity() | setPopularity(Integer popularity) |
| `PreviewUrl` | `String` | Optional | A link to a 30 second preview (MP3 format) of the track. Can be `null` | String getPreviewUrl() | setPreviewUrl(String previewUrl) |
| `TrackNumber` | `Integer` | Optional | The number of the track. If an album has several discs, the track number is the number on the specified disc. | Integer getTrackNumber() | setTrackNumber(Integer trackNumber) |
| `Type` | [`Type3`](../../doc/models/type-3.md) | Optional | - | Type3 getType() | setType(Type3 type) |
| `Uri` | `String` | Optional | The [Spotify URI](https://developer.spotify.com/documentation/web-api/concepts/spotify-uris-ids) for the track. | String getUri() | setUri(String uri) |
| `IsLocal` | `Boolean` | Optional | Whether or not the track is from a local file. | Boolean getIsLocal() | setIsLocal(Boolean isLocal) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.models.AlbumRestrictionObject;
import com.spotify.api.models.AlbumType;
import com.spotify.api.models.ArtistObject;
import com.spotify.api.models.ExternalUrlObject;
import com.spotify.api.models.FollowersObject;
import com.spotify.api.models.ImageObject;
import com.spotify.api.models.Reason;
import com.spotify.api.models.ReleaseDatePrecision;
import com.spotify.api.models.SimplifiedAlbumObject;
import com.spotify.api.models.SimplifiedArtistObject;
import com.spotify.api.models.TrackObject;
import com.spotify.api.models.Type;
import com.spotify.api.models.Type2;
import java.io.IOException;
import java.util.Arrays;

TrackObject trackObject = new TrackObject.Builder()
    .album(new SimplifiedAlbumObject.Builder(
        AlbumType.SINGLE,
        170,
        Arrays.asList(
            "available_markets2",
            "available_markets3"
        ),
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
            .build()
        ),
        "name8",
        "release_date6",
        ReleaseDatePrecision.DAY,
        Type2.ALBUM,
        "uri2",
        Arrays.asList(
            new SimplifiedArtistObject.Builder()
                .externalUrls(new ExternalUrlObject.Builder()
                    .spotify("spotify6")
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                    .build())
                .href("href2")
                .id("id0")
                .name("name0")
                .type(Type.ARTIST)
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build(),
            new SimplifiedArtistObject.Builder()
                .externalUrls(new ExternalUrlObject.Builder()
                    .spotify("spotify6")
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                    .build())
                .href("href2")
                .id("id0")
                .name("name0")
                .type(Type.ARTIST)
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build()
        )
    )
    .restrictions(new AlbumRestrictionObject.Builder()
            .reason(Reason.EXPLICIT)
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build())
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build())
    .artists(Arrays.asList(
        new ArtistObject.Builder()
            .externalUrls(new ExternalUrlObject.Builder()
                .spotify("spotify6")
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build())
            .followers(new FollowersObject.Builder()
                .href("href0")
                .total(82)
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build())
            .genres(Arrays.asList(
                "genres7",
                "genres8"
            ))
            .href("href2")
            .id("id0")
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build(),
        new ArtistObject.Builder()
            .externalUrls(new ExternalUrlObject.Builder()
                .spotify("spotify6")
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build())
            .followers(new FollowersObject.Builder()
                .href("href0")
                .total(82)
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build())
            .genres(Arrays.asList(
                "genres7",
                "genres8"
            ))
            .href("href2")
            .id("id0")
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build()
    ))
    .availableMarkets(Arrays.asList(
        "available_markets2",
        "available_markets3",
        "available_markets4"
    ))
    .discNumber(182)
    .durationMs(246)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

