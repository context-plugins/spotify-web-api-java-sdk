
# Followers Object

*This model accepts additional fields of type Object.*

## Structure

`FollowersObject`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Href` | `String` | Optional | This will always be set to null, as the Web API does not support it at the moment. | String getHref() | setHref(String href) |
| `Total` | `Integer` | Optional | The total number of followers. | Integer getTotal() | setTotal(Integer total) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.models.FollowersObject;
import java.io.IOException;

FollowersObject followersObject = new FollowersObject.Builder()
    .href("href2")
    .total(62)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

