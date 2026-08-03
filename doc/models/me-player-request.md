
# Me Player Request

*This model accepts additional fields of type Object.*

## Structure

`MePlayerRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `DeviceIds` | `List<String>` | Required | A JSON array containing the ID of the device on which playback should be started/transferred.<br/>For example:`{device_ids:["74ASZWbe4lXaubB36ztrGX"]}`<br/>_**Note**: Although an array is accepted, only a single device_id is currently supported. Supplying more than one will return `400 Bad Request`_ | List<String> getDeviceIds() | setDeviceIds(List<String> deviceIds) |
| `Play` | `Boolean` | Optional | **true**: ensure playback happens on new device.<br/>**false** or not provided: keep the current playback state. | Boolean getPlay() | setPlay(Boolean play) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.models.MePlayerRequest;
import java.io.IOException;
import java.util.Arrays;

MePlayerRequest mePlayerRequest = new MePlayerRequest.Builder(
    Arrays.asList(
        "74ASZWbe4lXaubB36ztrGX"
    )
)
.play(false)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

