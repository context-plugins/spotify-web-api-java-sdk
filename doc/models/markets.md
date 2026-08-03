
# Markets

*This model accepts additional fields of type Object.*

## Structure

`Markets`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Markets` | `List<String>` | Optional | - | List<String> getMarkets() | setMarkets(List<String> markets) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.models.Markets;
import java.io.IOException;
import java.util.Arrays;

Markets markets = new Markets.Builder()
    .markets(Arrays.asList(
        "CA",
        "BR",
        "IT"
    ))
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

