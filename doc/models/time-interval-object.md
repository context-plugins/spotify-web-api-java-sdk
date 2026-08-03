
# Time Interval Object

*This model accepts additional fields of type Object.*

## Structure

`TimeIntervalObject`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Start` | `Double` | Optional | The starting point (in seconds) of the time interval. | Double getStart() | setStart(Double start) |
| `Duration` | `Double` | Optional | The duration (in seconds) of the time interval. | Double getDuration() | setDuration(Double duration) |
| `Confidence` | `Double` | Optional | The confidence, from 0.0 to 1.0, of the reliability of the interval.<br><br>**Constraints**: `>= 0`, `<= 1` | Double getConfidence() | setConfidence(Double confidence) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.models.TimeIntervalObject;
import java.io.IOException;

TimeIntervalObject timeIntervalObject = new TimeIntervalObject.Builder()
    .start(0.49567D)
    .duration(2.18749D)
    .confidence(0.925D)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

