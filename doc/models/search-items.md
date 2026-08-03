
# Search Items

*This model accepts additional fields of type Object.*

## Structure

`SearchItems`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Tracks` | [`PagingTrackObject`](../../doc/models/paging-track-object.md) | Optional | - | PagingTrackObject getTracks() | setTracks(PagingTrackObject tracks) |
| `Artists` | [`PagingArtistObject`](../../doc/models/paging-artist-object.md) | Optional | - | PagingArtistObject getArtists() | setArtists(PagingArtistObject artists) |
| `Albums` | [`PagingSimplifiedAlbumObject`](../../doc/models/paging-simplified-album-object.md) | Optional | - | PagingSimplifiedAlbumObject getAlbums() | setAlbums(PagingSimplifiedAlbumObject albums) |
| `Playlists` | [`PagingPlaylistObject`](../../doc/models/paging-playlist-object.md) | Optional | - | PagingPlaylistObject getPlaylists() | setPlaylists(PagingPlaylistObject playlists) |
| `Shows` | [`PagingSimplifiedShowObject`](../../doc/models/paging-simplified-show-object.md) | Optional | - | PagingSimplifiedShowObject getShows() | setShows(PagingSimplifiedShowObject shows) |
| `Episodes` | [`PagingSimplifiedEpisodeObject`](../../doc/models/paging-simplified-episode-object.md) | Optional | - | PagingSimplifiedEpisodeObject getEpisodes() | setEpisodes(PagingSimplifiedEpisodeObject episodes) |
| `Audiobooks` | [`PagingSimplifiedAudiobookObject`](../../doc/models/paging-simplified-audiobook-object.md) | Optional | - | PagingSimplifiedAudiobookObject getAudiobooks() | setAudiobooks(PagingSimplifiedAudiobookObject audiobooks) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.models.AlbumRestrictionObject;
import com.spotify.api.models.AlbumType;
import com.spotify.api.models.ArtistObject;
import com.spotify.api.models.CopyrightObject;
import com.spotify.api.models.ExternalUrlObject;
import com.spotify.api.models.FollowersObject;
import com.spotify.api.models.ImageObject;
import com.spotify.api.models.PagingArtistObject;
import com.spotify.api.models.PagingPlaylistObject;
import com.spotify.api.models.PagingSimplifiedAlbumObject;
import com.spotify.api.models.PagingSimplifiedShowObject;
import com.spotify.api.models.PagingTrackObject;
import com.spotify.api.models.Reason;
import com.spotify.api.models.ReleaseDatePrecision;
import com.spotify.api.models.SearchItems;
import com.spotify.api.models.ShowBase;
import com.spotify.api.models.SimplifiedAlbumObject;
import com.spotify.api.models.SimplifiedArtistObject;
import com.spotify.api.models.SimplifiedPlaylistObject;
import com.spotify.api.models.TrackObject;
import com.spotify.api.models.Type;
import com.spotify.api.models.Type2;
import com.spotify.api.models.Type6;
import java.io.IOException;
import java.util.Arrays;

SearchItems searchItems = new SearchItems.Builder()
    .tracks(new PagingTrackObject.Builder(
        "href6",
        142,
        "next8",
        238,
        "previous2",
        236,
        Arrays.asList(
            new TrackObject.Builder()
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
                        .build()
                ))
                .availableMarkets(Arrays.asList(
                    "available_markets2"
                ))
                .discNumber(244)
                .durationMs(52)
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build()
        )
    )
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build())
    .artists(new PagingArtistObject.Builder(
        "href2",
        214,
        "next2",
        54,
        "previous8",
        52,
        Arrays.asList(
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
                    "genres5",
                    "genres6"
                ))
                .href("href0")
                .id("id8")
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
                    "genres5",
                    "genres6"
                ))
                .href("href0")
                .id("id8")
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
                    "genres5",
                    "genres6"
                ))
                .href("href0")
                .id("id8")
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build()
        )
    )
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build())
    .albums(new PagingSimplifiedAlbumObject.Builder(
        "href0",
        0,
        "next4",
        96,
        "previous6",
        94,
        Arrays.asList(
            new SimplifiedAlbumObject.Builder(
                AlbumType.ALBUM,
                196,
                Arrays.asList(
                    "available_markets2"
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
                    .build(),
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
                ReleaseDatePrecision.MONTH,
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
                        .build()
                )
            )
            .restrictions(new AlbumRestrictionObject.Builder()
                    .reason(Reason.EXPLICIT)
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                    .build())
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build()
        )
    )
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build())
    .playlists(new PagingPlaylistObject.Builder(
        "href2",
        68,
        "next2",
        164,
        "previous8",
        162,
        Arrays.asList(
            new SimplifiedPlaylistObject.Builder()
                .collaborative(false)
                .description("description2")
                .externalUrls(new ExternalUrlObject.Builder()
                    .spotify("spotify6")
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                    .build())
                .href("href0")
                .id("id8")
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build(),
            new SimplifiedPlaylistObject.Builder()
                .collaborative(false)
                .description("description2")
                .externalUrls(new ExternalUrlObject.Builder()
                    .spotify("spotify6")
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                    .build())
                .href("href0")
                .id("id8")
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build(),
            new SimplifiedPlaylistObject.Builder()
                .collaborative(false)
                .description("description2")
                .externalUrls(new ExternalUrlObject.Builder()
                    .spotify("spotify6")
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                    .build())
                .href("href0")
                .id("id8")
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build()
        )
    )
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build())
    .shows(new PagingSimplifiedShowObject.Builder(
        "href0",
        248,
        "next6",
        88,
        "previous6",
        86,
        Arrays.asList(
            new ShowBase.Builder(
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
                    .build()
                ),
                false,
                Arrays.asList(
                    "languages5"
                ),
                "media_type4",
                "name8",
                "publisher4",
                Type6.SHOW,
                "uri2",
                166
            )
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build(),
            new ShowBase.Builder(
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
                    .build()
                ),
                false,
                Arrays.asList(
                    "languages5"
                ),
                "media_type4",
                "name8",
                "publisher4",
                Type6.SHOW,
                "uri2",
                166
            )
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build(),
            new ShowBase.Builder(
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
                    .build()
                ),
                false,
                Arrays.asList(
                    "languages5"
                ),
                "media_type4",
                "name8",
                "publisher4",
                Type6.SHOW,
                "uri2",
                166
            )
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build()
        )
    )
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build())
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

