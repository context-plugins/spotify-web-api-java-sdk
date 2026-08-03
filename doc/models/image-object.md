
# Image Object

*This model accepts additional fields of type Object.*

## Structure

`ImageObject`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Url` | `String` | Required | The source URL of the image. | String getUrl() | setUrl(String url) |
| `Height` | `Integer` | Required | The image height in pixels. | Integer getHeight() | setHeight(Integer height) |
| `Width` | `Integer` | Required | The image width in pixels. | Integer getWidth() | setWidth(Integer width) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.models.ImageObject;
import java.io.IOException;

ImageObject imageObject = new ImageObject.Builder(
    "https://i.scdn.co/image/ab67616d00001e02ff9ca10b55ce82ae553c8228\n",
    300,
    300
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

