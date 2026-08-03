
# Meta

*This model accepts additional fields of type Object.*

## Structure

`Meta`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `AnalyzerVersion` | `String` | Optional | The version of the Analyzer used to analyze this track. | String getAnalyzerVersion() | setAnalyzerVersion(String analyzerVersion) |
| `Platform` | `String` | Optional | The platform used to read the track's audio data. | String getPlatform() | setPlatform(String platform) |
| `DetailedStatus` | `String` | Optional | A detailed status code for this track. If analysis data is missing, this code may explain why. | String getDetailedStatus() | setDetailedStatus(String detailedStatus) |
| `StatusCode` | `Integer` | Optional | The return code of the analyzer process. 0 if successful, 1 if any errors occurred. | Integer getStatusCode() | setStatusCode(Integer statusCode) |
| `Timestamp` | `Long` | Optional | The Unix timestamp (in seconds) at which this track was analyzed. | Long getTimestamp() | setTimestamp(Long timestamp) |
| `AnalysisTime` | `Double` | Optional | The amount of time taken to analyze this track. | Double getAnalysisTime() | setAnalysisTime(Double analysisTime) |
| `InputProcess` | `String` | Optional | The method used to read the track's audio data. | String getInputProcess() | setInputProcess(String inputProcess) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.models.Meta;
import java.io.IOException;

Meta meta = new Meta.Builder()
    .analyzerVersion("4.0.0")
    .platform("Linux")
    .detailedStatus("OK")
    .statusCode(0)
    .timestamp(1495193577L)
    .analysisTime(6.93906D)
    .inputProcess("libvorbisfile L+R 44100->22050")
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

