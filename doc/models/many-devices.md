
# Many Devices

*This model accepts additional fields of type Object.*

## Structure

`ManyDevices`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Devices` | [`List<DeviceObject>`](../../doc/models/device-object.md) | Required | - | List<DeviceObject> getDevices() | setDevices(List<DeviceObject> devices) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.models.DeviceObject;
import com.spotify.api.models.ManyDevices;
import java.io.IOException;
import java.util.Arrays;

ManyDevices manyDevices = new ManyDevices.Builder(
    Arrays.asList(
        new DeviceObject.Builder()
            .id("id4")
            .isActive(false)
            .isPrivateSession(false)
            .isRestricted(false)
            .name("Kitchen speaker")
            .type("computer")
            .volumePercent(59)
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build()
    )
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

