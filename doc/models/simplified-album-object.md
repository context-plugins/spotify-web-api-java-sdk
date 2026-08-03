
# Simplified Album Object

*This model accepts additional fields of type Object.*

## Structure

`SimplifiedAlbumObject`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `AlbumType` | [`AlbumType`](../../doc/models/album-type.md) | Required | - | AlbumType getAlbumType() | setAlbumType(AlbumType albumType) |
| `TotalTracks` | `int` | Required | The number of tracks in the album. | int getTotalTracks() | setTotalTracks(int totalTracks) |
| `AvailableMarkets` | `List<String>` | Required | The markets in which the album is available: [ISO 3166-1 alpha-2 country codes](http://en.wikipedia.org/wiki/ISO_3166-1_alpha-2). _**NOTE**: an album is considered available in a market when at least 1 of its tracks is available in that market._ | List<String> getAvailableMarkets() | setAvailableMarkets(List<String> availableMarkets) |
| `ExternalUrls` | [`ExternalUrlObject`](../../doc/models/external-url-object.md) | Required | - | ExternalUrlObject getExternalUrls() | setExternalUrls(ExternalUrlObject externalUrls) |
| `Href` | `String` | Required | A link to the Web API endpoint providing full details of the album. | String getHref() | setHref(String href) |
| `Id` | `String` | Required | The [Spotify ID](https://developer.spotify.com/documentation/web-api/concepts/spotify-uris-ids) for the album. | String getId() | setId(String id) |
| `Images` | [`List<ImageObject>`](../../doc/models/image-object.md) | Required | The cover art for the album in various sizes, widest first. | List<ImageObject> getImages() | setImages(List<ImageObject> images) |
| `Name` | `String` | Required | The name of the album. In case of an album takedown, the value may be an empty string. | String getName() | setName(String name) |
| `ReleaseDate` | `String` | Required | The date the album was first released. | String getReleaseDate() | setReleaseDate(String releaseDate) |
| `ReleaseDatePrecision` | [`ReleaseDatePrecision`](../../doc/models/release-date-precision.md) | Required | - | ReleaseDatePrecision getReleaseDatePrecision() | setReleaseDatePrecision(ReleaseDatePrecision releaseDatePrecision) |
| `Restrictions` | [`AlbumRestrictionObject`](../../doc/models/album-restriction-object.md) | Optional | - | AlbumRestrictionObject getRestrictions() | setRestrictions(AlbumRestrictionObject restrictions) |
| `Type` | [`Type2`](../../doc/models/type-2.md) | Required | - | Type2 getType() | setType(Type2 type) |
| `Uri` | `String` | Required | The [Spotify URI](https://developer.spotify.com/documentation/web-api/concepts/spotify-uris-ids) for the album. | String getUri() | setUri(String uri) |
| `Artists` | [`List<SimplifiedArtistObject>`](../../doc/models/simplified-artist-object.md) | Required | The artists of the album. Each artist object includes a link in `href` to more detailed information about the artist. | List<SimplifiedArtistObject> getArtists() | setArtists(List<SimplifiedArtistObject> artists) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.models.AlbumRestrictionObject;
import com.spotify.api.models.AlbumType;
import com.spotify.api.models.ExternalUrlObject;
import com.spotify.api.models.ImageObject;
import com.spotify.api.models.Reason;
import com.spotify.api.models.ReleaseDatePrecision;
import com.spotify.api.models.SimplifiedAlbumObject;
import com.spotify.api.models.SimplifiedArtistObject;
import com.spotify.api.models.Type;
import com.spotify.api.models.Type2;
import java.io.IOException;
import java.util.Arrays;

SimplifiedAlbumObject simplifiedAlbumObject = new SimplifiedAlbumObject.Builder(
    AlbumType.SINGLE,
    9,
    Arrays.asList(
        "CA",
        "BR",
        "IT"
    ),
    new ExternalUrlObject.Builder()
        .spotify("spotify6")
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build(),
    "href4",
    "2up3OPMp9Tb4dAKM2erWXQ",
    Arrays.asList(
        new ImageObject.Builder(
            "https://i.scdn.co/image/ab67616d00001e02ff9ca10b55ce82ae553c8228\n",
            300,
            300
        )
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build()
    ),
    "name2",
    "1981-12",
    ReleaseDatePrecision.DAY,
    Type2.ALBUM,
    "spotify:album:2up3OPMp9Tb4dAKM2erWXQ",
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
            .build()
    )
)
.restrictions(new AlbumRestrictionObject.Builder()
        .reason(Reason.EXPLICIT)
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build())
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

