
# Playlists Tracks Request 1

*This model accepts additional fields of type Object.*

## Structure

`PlaylistsTracksRequest1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Uris` | `List<String>` | Optional | - | List<String> getUris() | setUris(List<String> uris) |
| `RangeStart` | `Integer` | Optional | The position of the first item to be reordered. | Integer getRangeStart() | setRangeStart(Integer rangeStart) |
| `InsertBefore` | `Integer` | Optional | The position where the items should be inserted.<br/>To reorder the items to the end of the playlist, simply set _insert_before_ to the position after the last item.<br/>Examples:<br/>To reorder the first item to the last position in a playlist with 10 items, set _range_start_ to 0, and _insert_before_ to 10.<br/>To reorder the last item in a playlist with 10 items to the start of the playlist, set _range_start_ to 9, and _insert_before_ to 0. | Integer getInsertBefore() | setInsertBefore(Integer insertBefore) |
| `RangeLength` | `Integer` | Optional | The amount of items to be reordered. Defaults to 1 if not set.<br/>The range of items to be reordered begins from the _range_start_ position, and includes the _range_length_ subsequent items.<br/>Example:<br/>To move the items at index 9-10 to the start of the playlist, _range_start_ is set to 9, and _range_length_ is set to 2. | Integer getRangeLength() | setRangeLength(Integer rangeLength) |
| `SnapshotId` | `String` | Optional | The playlist's snapshot ID against which you want to make the changes. | String getSnapshotId() | setSnapshotId(String snapshotId) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.models.PlaylistsTracksRequest1;
import java.io.IOException;
import java.util.Arrays;

PlaylistsTracksRequest1 playlistsTracksRequest1 = new PlaylistsTracksRequest1.Builder()
    .uris(Arrays.asList(
        "uris9"
    ))
    .rangeStart(1)
    .insertBefore(3)
    .rangeLength(2)
    .snapshotId("snapshot_id4")
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

