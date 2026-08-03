
# Segment Object

*This model accepts additional fields of type Object.*

## Structure

`SegmentObject`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Start` | `Double` | Optional | The starting point (in seconds) of the segment. | Double getStart() | setStart(Double start) |
| `Duration` | `Double` | Optional | The duration (in seconds) of the segment. | Double getDuration() | setDuration(Double duration) |
| `Confidence` | `Double` | Optional | The confidence, from 0.0 to 1.0, of the reliability of the segmentation. Segments of the song which are difficult to logically segment (e.g: noise) may correspond to low values in this field.<br><br>**Constraints**: `>= 0`, `<= 1` | Double getConfidence() | setConfidence(Double confidence) |
| `LoudnessStart` | `Double` | Optional | The onset loudness of the segment in decibels (dB). Combined with `loudness_max` and `loudness_max_time`, these components can be used to describe the "attack" of the segment. | Double getLoudnessStart() | setLoudnessStart(Double loudnessStart) |
| `LoudnessMax` | `Double` | Optional | The peak loudness of the segment in decibels (dB). Combined with `loudness_start` and `loudness_max_time`, these components can be used to describe the "attack" of the segment. | Double getLoudnessMax() | setLoudnessMax(Double loudnessMax) |
| `LoudnessMaxTime` | `Double` | Optional | The segment-relative offset of the segment peak loudness in seconds. Combined with `loudness_start` and `loudness_max`, these components can be used to desctibe the "attack" of the segment. | Double getLoudnessMaxTime() | setLoudnessMaxTime(Double loudnessMaxTime) |
| `LoudnessEnd` | `Double` | Optional | The offset loudness of the segment in decibels (dB). This value should be equivalent to the loudness_start of the following segment. | Double getLoudnessEnd() | setLoudnessEnd(Double loudnessEnd) |
| `Pitches` | `List<Double>` | Optional | Pitch content is given by a “chroma” vector, corresponding to the 12 pitch classes C, C#, D to B, with values ranging from 0 to 1 that describe the relative dominance of every pitch in the chromatic scale. For example a C Major chord would likely be represented by large values of C, E and G (i.e. classes 0, 4, and 7).<br><br>Vectors are normalized to 1 by their strongest dimension, therefore noisy sounds are likely represented by values that are all close to 1, while pure tones are described by one value at 1 (the pitch) and others near 0.<br>As can be seen below, the 12 vector indices are a combination of low-power spectrum values at their respective pitch frequencies.<br>![pitch vector](https://developer.spotify.com/assets/audio/Pitch_vector.png)<br><br>**Constraints**: `>= 0`, `<= 1` | List<Double> getPitches() | setPitches(List<Double> pitches) |
| `Timbre` | `List<Double>` | Optional | Timbre is the quality of a musical note or sound that distinguishes different types of musical instruments, or voices. It is a complex notion also referred to as sound color, texture, or tone quality, and is derived from the shape of a segment’s spectro-temporal surface, independently of pitch and loudness. The timbre feature is a vector that includes 12 unbounded values roughly centered around 0. Those values are high level abstractions of the spectral surface, ordered by degree of importance.<br><br>For completeness however, the first dimension represents the average loudness of the segment; second emphasizes brightness; third is more closely correlated to the flatness of a sound; fourth to sounds with a stronger attack; etc. See an image below representing the 12 basis functions (i.e. template segments).<br>![timbre basis functions](https://developer.spotify.com/assets/audio/Timbre_basis_functions.png)<br><br>The actual timbre of the segment is best described as a linear combination of these 12 basis functions weighted by the coefficient values: timbre = c1 x b1 + c2 x b2 + ... + c12 x b12, where c1 to c12 represent the 12 coefficients and b1 to b12 the 12 basis functions as displayed below. Timbre vectors are best used in comparison with each other. | List<Double> getTimbre() | setTimbre(List<Double> timbre) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.models.SegmentObject;
import java.io.IOException;
import java.util.Arrays;

SegmentObject segmentObject = new SegmentObject.Builder()
    .start(0.70154D)
    .duration(0.19891D)
    .confidence(0.435D)
    .loudnessStart(-23.053D)
    .loudnessMax(-14.25D)
    .loudnessMaxTime(0.07305D)
    .loudnessEnd(0D)
    .pitches(Arrays.asList(
        0.212D,
        0.141D,
        0.294D
    ))
    .timbre(Arrays.asList(
        42.115D,
        64.373D,
        -0.233D
    ))
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

