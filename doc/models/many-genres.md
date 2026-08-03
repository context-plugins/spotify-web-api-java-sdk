
# Many Genres

*This model accepts additional fields of type Object.*

## Structure

`ManyGenres`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Genres` | `List<String>` | Required | - | List<String> getGenres() | setGenres(List<String> genres) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.models.ManyGenres;
import java.io.IOException;
import java.util.Arrays;

ManyGenres manyGenres = new ManyGenres.Builder(
    Arrays.asList(
        "alternative",
        "samba"
    )
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

