
# Track Restriction Object

*This model accepts additional fields of type Object.*

## Structure

`TrackRestrictionObject`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Reason` | `String` | Optional | The reason for the restriction. Supported values:<br><br>- `market` - The content item is not available in the given market.<br>- `product` - The content item is not available for the user's subscription type.<br>- `explicit` - The content item is explicit and the user's account is set to not play explicit content.<br><br>Additional reasons may be added in the future.<br>**Note**: If you use this field, make sure that your application safely handles unknown values. | String getReason() | setReason(String reason) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.models.TrackRestrictionObject;
import java.io.IOException;

TrackRestrictionObject trackRestrictionObject = new TrackRestrictionObject.Builder()
    .reason("reason6")
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

