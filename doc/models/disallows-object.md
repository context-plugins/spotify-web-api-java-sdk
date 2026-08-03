
# Disallows Object

*This model accepts additional fields of type Object.*

## Structure

`DisallowsObject`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `InterruptingPlayback` | `Boolean` | Optional | Interrupting playback. Optional field. | Boolean getInterruptingPlayback() | setInterruptingPlayback(Boolean interruptingPlayback) |
| `Pausing` | `Boolean` | Optional | Pausing. Optional field. | Boolean getPausing() | setPausing(Boolean pausing) |
| `Resuming` | `Boolean` | Optional | Resuming. Optional field. | Boolean getResuming() | setResuming(Boolean resuming) |
| `Seeking` | `Boolean` | Optional | Seeking playback location. Optional field. | Boolean getSeeking() | setSeeking(Boolean seeking) |
| `SkippingNext` | `Boolean` | Optional | Skipping to the next context. Optional field. | Boolean getSkippingNext() | setSkippingNext(Boolean skippingNext) |
| `SkippingPrev` | `Boolean` | Optional | Skipping to the previous context. Optional field. | Boolean getSkippingPrev() | setSkippingPrev(Boolean skippingPrev) |
| `TogglingRepeatContext` | `Boolean` | Optional | Toggling repeat context flag. Optional field. | Boolean getTogglingRepeatContext() | setTogglingRepeatContext(Boolean togglingRepeatContext) |
| `TogglingShuffle` | `Boolean` | Optional | Toggling shuffle flag. Optional field. | Boolean getTogglingShuffle() | setTogglingShuffle(Boolean togglingShuffle) |
| `TogglingRepeatTrack` | `Boolean` | Optional | Toggling repeat track flag. Optional field. | Boolean getTogglingRepeatTrack() | setTogglingRepeatTrack(Boolean togglingRepeatTrack) |
| `TransferringPlayback` | `Boolean` | Optional | Transfering playback between devices. Optional field. | Boolean getTransferringPlayback() | setTransferringPlayback(Boolean transferringPlayback) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.models.DisallowsObject;
import java.io.IOException;

DisallowsObject disallowsObject = new DisallowsObject.Builder()
    .interruptingPlayback(false)
    .pausing(false)
    .resuming(false)
    .seeking(false)
    .skippingNext(false)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

