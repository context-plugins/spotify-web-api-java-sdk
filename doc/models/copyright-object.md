
# Copyright Object

*This model accepts additional fields of type Object.*

## Structure

`CopyrightObject`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Text` | `String` | Optional | The copyright text for this content. | String getText() | setText(String text) |
| `Type` | `String` | Optional | The type of copyright: `C` = the copyright, `P` = the sound recording (performance) copyright. | String getType() | setType(String type) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.models.CopyrightObject;
import java.io.IOException;

CopyrightObject copyrightObject = new CopyrightObject.Builder()
    .text("text4")
    .type("type4")
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

