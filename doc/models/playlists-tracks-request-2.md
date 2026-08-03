
# Playlists Tracks Request 2

*This model accepts additional fields of type Object.*

## Structure

`PlaylistsTracksRequest2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Tracks` | [`List<Track1>`](../../doc/models/track-1.md) | Required | An array of objects containing [Spotify URIs](https://developer.spotify.com/documentation/web-api/concepts/spotify-uris-ids) of the tracks or episodes to remove.<br>For example: `{ "tracks": [{ "uri": "spotify:track:4iV5W9uYEdYUVa79Axb7Rh" },{ "uri": "spotify:track:1301WleyT98MSxVHPZCA6M" }] }`. A maximum of 100 objects can be sent at once. | List<Track1> getTracks() | setTracks(List<Track1> tracks) |
| `SnapshotId` | `String` | Optional | The playlist's snapshot ID against which you want to make the changes.<br>The API will validate that the specified items exist and in the specified positions and make the changes,<br>even if more recent changes have been made to the playlist. | String getSnapshotId() | setSnapshotId(String snapshotId) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.models.PlaylistsTracksRequest2;
import com.spotify.api.models.Track1;
import java.io.IOException;
import java.util.Arrays;

PlaylistsTracksRequest2 playlistsTracksRequest2 = new PlaylistsTracksRequest2.Builder(
    Arrays.asList(
        new Track1.Builder()
            .uri("uri8")
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build()
    )
)
.snapshotId("snapshot_id8")
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

