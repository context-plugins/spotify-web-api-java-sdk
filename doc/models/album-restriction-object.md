
# Album Restriction Object

*This model accepts additional fields of type Object.*

## Structure

`AlbumRestrictionObject`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Reason` | [`Reason`](../../doc/models/reason.md) | Optional | - | Reason getReason() | setReason(Reason reason) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.models.AlbumRestrictionObject;
import com.spotify.api.models.Reason;
import java.io.IOException;

AlbumRestrictionObject albumRestrictionObject = new AlbumRestrictionObject.Builder()
    .reason(Reason.MARKET)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

