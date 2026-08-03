
# Section Object

*This model accepts additional fields of type Object.*

## Structure

`SectionObject`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Start` | `Double` | Optional | The starting point (in seconds) of the section. | Double getStart() | setStart(Double start) |
| `Duration` | `Double` | Optional | The duration (in seconds) of the section. | Double getDuration() | setDuration(Double duration) |
| `Confidence` | `Double` | Optional | The confidence, from 0.0 to 1.0, of the reliability of the section's "designation".<br><br>**Constraints**: `>= 0`, `<= 1` | Double getConfidence() | setConfidence(Double confidence) |
| `Loudness` | `Double` | Optional | The overall loudness of the section in decibels (dB). Loudness values are useful for comparing relative loudness of sections within tracks. | Double getLoudness() | setLoudness(Double loudness) |
| `Tempo` | `Double` | Optional | The overall estimated tempo of the section in beats per minute (BPM). In musical terminology, tempo is the speed or pace of a given piece and derives directly from the average beat duration. | Double getTempo() | setTempo(Double tempo) |
| `TempoConfidence` | `Double` | Optional | The confidence, from 0.0 to 1.0, of the reliability of the tempo. Some tracks contain tempo changes or sounds which don't contain tempo (like pure speech) which would correspond to a low value in this field.<br><br>**Constraints**: `>= 0`, `<= 1` | Double getTempoConfidence() | setTempoConfidence(Double tempoConfidence) |
| `Key` | `Integer` | Optional | The estimated overall key of the section. The values in this field ranging from 0 to 11 mapping to pitches using standard Pitch Class notation (E.g. 0 = C, 1 = C♯/D♭, 2 = D, and so on). If no key was detected, the value is -1. | Integer getKey() | setKey(Integer key) |
| `KeyConfidence` | `Double` | Optional | The confidence, from 0.0 to 1.0, of the reliability of the key. Songs with many key changes may correspond to low values in this field.<br><br>**Constraints**: `>= 0`, `<= 1` | Double getKeyConfidence() | setKeyConfidence(Double keyConfidence) |
| `Mode` | [`Mode`](../../doc/models/mode.md) | Optional | - | Mode getMode() | setMode(Mode mode) |
| `ModeConfidence` | `Double` | Optional | The confidence, from 0.0 to 1.0, of the reliability of the `mode`.<br><br>**Constraints**: `>= 0`, `<= 1` | Double getModeConfidence() | setModeConfidence(Double modeConfidence) |
| `TimeSignature` | `Integer` | Optional | An estimated time signature. The time signature (meter) is a notational convention to specify how many beats are in each bar (or measure). The time signature ranges from 3 to 7 indicating time signatures of "3/4", to "7/4".<br><br>**Constraints**: `>= 3`, `<= 7` | Integer getTimeSignature() | setTimeSignature(Integer timeSignature) |
| `TimeSignatureConfidence` | `Double` | Optional | The confidence, from 0.0 to 1.0, of the reliability of the `time_signature`. Sections with time signature changes may correspond to low values in this field.<br><br>**Constraints**: `>= 0`, `<= 1` | Double getTimeSignatureConfidence() | setTimeSignatureConfidence(Double timeSignatureConfidence) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.models.SectionObject;
import java.io.IOException;

SectionObject sectionObject = new SectionObject.Builder()
    .start(0D)
    .duration(6.97092D)
    .confidence(1D)
    .loudness(-14.938D)
    .tempo(113.178D)
    .tempoConfidence(0.647D)
    .key(9)
    .keyConfidence(0.297D)
    .modeConfidence(0.471D)
    .timeSignature(4)
    .timeSignatureConfidence(1D)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

