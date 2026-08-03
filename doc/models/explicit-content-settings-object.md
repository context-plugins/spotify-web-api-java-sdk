
# Explicit Content Settings Object

*This model accepts additional fields of type Object.*

## Structure

`ExplicitContentSettingsObject`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `FilterEnabled` | `Boolean` | Optional | When `true`, indicates that explicit content should not be played. | Boolean getFilterEnabled() | setFilterEnabled(Boolean filterEnabled) |
| `FilterLocked` | `Boolean` | Optional | When `true`, indicates that the explicit content setting is locked and can't be changed by the user. | Boolean getFilterLocked() | setFilterLocked(Boolean filterLocked) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.models.ExplicitContentSettingsObject;
import java.io.IOException;

ExplicitContentSettingsObject explicitContentSettingsObject = new ExplicitContentSettingsObject.Builder()
    .filterEnabled(false)
    .filterLocked(false)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

