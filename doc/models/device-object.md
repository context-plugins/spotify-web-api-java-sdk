
# Device Object

*This model accepts additional fields of type Object.*

## Structure

`DeviceObject`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Id` | `String` | Optional | The device ID. This ID is unique and persistent to some extent. However, this is not guaranteed and any cached `device_id` should periodically be cleared out and refetched as necessary. | String getId() | setId(String id) |
| `IsActive` | `Boolean` | Optional | If this device is the currently active device. | Boolean getIsActive() | setIsActive(Boolean isActive) |
| `IsPrivateSession` | `Boolean` | Optional | If this device is currently in a private session. | Boolean getIsPrivateSession() | setIsPrivateSession(Boolean isPrivateSession) |
| `IsRestricted` | `Boolean` | Optional | Whether controlling this device is restricted. At present if this is "true" then no Web API commands will be accepted by this device. | Boolean getIsRestricted() | setIsRestricted(Boolean isRestricted) |
| `Name` | `String` | Optional | A human-readable name for the device. Some devices have a name that the user can configure (e.g. \"Loudest speaker\") and some devices have a generic name associated with the manufacturer or device model. | String getName() | setName(String name) |
| `Type` | `String` | Optional | Device type, such as "computer", "smartphone" or "speaker". | String getType() | setType(String type) |
| `VolumePercent` | `Integer` | Optional | The current volume in percent.<br><br>**Constraints**: `>= 0`, `<= 100` | Integer getVolumePercent() | setVolumePercent(Integer volumePercent) |
| `SupportsVolume` | `Boolean` | Optional | If this device can be used to set the volume. | Boolean getSupportsVolume() | setSupportsVolume(Boolean supportsVolume) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.models.DeviceObject;
import java.io.IOException;

DeviceObject deviceObject = new DeviceObject.Builder()
    .id("id0")
    .isActive(false)
    .isPrivateSession(false)
    .isRestricted(false)
    .name("Kitchen speaker")
    .type("computer")
    .volumePercent(59)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

