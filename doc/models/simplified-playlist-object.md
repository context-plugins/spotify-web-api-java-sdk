
# Simplified Playlist Object

*This model accepts additional fields of type Object.*

## Structure

`SimplifiedPlaylistObject`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Collaborative` | `Boolean` | Optional | `true` if the owner allows other users to modify the playlist. | Boolean getCollaborative() | setCollaborative(Boolean collaborative) |
| `Description` | `String` | Optional | The playlist description. _Only returned for modified, verified playlists, otherwise_ `null`. | String getDescription() | setDescription(String description) |
| `ExternalUrls` | [`ExternalUrlObject`](../../doc/models/external-url-object.md) | Optional | - | ExternalUrlObject getExternalUrls() | setExternalUrls(ExternalUrlObject externalUrls) |
| `Href` | `String` | Optional | A link to the Web API endpoint providing full details of the playlist. | String getHref() | setHref(String href) |
| `Id` | `String` | Optional | The [Spotify ID](https://developer.spotify.com/documentation/web-api/concepts/spotify-uris-ids) for the playlist. | String getId() | setId(String id) |
| `Images` | [`List<ImageObject>`](../../doc/models/image-object.md) | Optional | Images for the playlist. The array may be empty or contain up to three images. The images are returned by size in descending order. See [Working with Playlists](https://developer.spotify.com/documentation/web-api/concepts/playlists). _**Note**: If returned, the source URL for the image (`url`) is temporary and will expire in less than a day._ | List<ImageObject> getImages() | setImages(List<ImageObject> images) |
| `Name` | `String` | Optional | The name of the playlist. | String getName() | setName(String name) |
| `Owner` | [`PlaylistOwnerObject`](../../doc/models/playlist-owner-object.md) | Optional | - | PlaylistOwnerObject getOwner() | setOwner(PlaylistOwnerObject owner) |
| `Public` | `Boolean` | Optional | The playlist's public/private status: `true` the playlist is public, `false` the playlist is private, `null` the playlist status is not relevant. For more about public/private status, see [Working with Playlists](https://developer.spotify.com/documentation/web-api/concepts/playlists) | Boolean getPublic() | setPublic(Boolean mPublic) |
| `SnapshotId` | `String` | Optional | The version identifier for the current playlist. Can be supplied in other requests to target a specific playlist version | String getSnapshotId() | setSnapshotId(String snapshotId) |
| `Tracks` | [`PlaylistTracksRefObject`](../../doc/models/playlist-tracks-ref-object.md) | Optional | - | PlaylistTracksRefObject getTracks() | setTracks(PlaylistTracksRefObject tracks) |
| `Type` | `String` | Optional | The object type: "playlist" | String getType() | setType(String type) |
| `Uri` | `String` | Optional | The [Spotify URI](https://developer.spotify.com/documentation/web-api/concepts/spotify-uris-ids) for the playlist. | String getUri() | setUri(String uri) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.models.ExternalUrlObject;
import com.spotify.api.models.SimplifiedPlaylistObject;
import java.io.IOException;

SimplifiedPlaylistObject simplifiedPlaylistObject = new SimplifiedPlaylistObject.Builder()
    .collaborative(false)
    .description("description0")
    .externalUrls(new ExternalUrlObject.Builder()
        .spotify("spotify6")
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build())
    .href("href8")
    .id("id0")
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

