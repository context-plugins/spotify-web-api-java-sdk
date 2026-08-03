
# Audio Analysis Object

*This model accepts additional fields of type Object.*

## Structure

`AudioAnalysisObject`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Meta` | [`Meta`](../../doc/models/meta.md) | Optional | - | Meta getMeta() | setMeta(Meta meta) |
| `Track` | [`Track`](../../doc/models/track.md) | Optional | - | Track getTrack() | setTrack(Track track) |
| `Bars` | [`List<TimeIntervalObject>`](../../doc/models/time-interval-object.md) | Optional | The time intervals of the bars throughout the track. A bar (or measure) is a segment of time defined as a given number of beats. | List<TimeIntervalObject> getBars() | setBars(List<TimeIntervalObject> bars) |
| `Beats` | [`List<TimeIntervalObject>`](../../doc/models/time-interval-object.md) | Optional | The time intervals of beats throughout the track. A beat is the basic time unit of a piece of music; for example, each tick of a metronome. Beats are typically multiples of tatums. | List<TimeIntervalObject> getBeats() | setBeats(List<TimeIntervalObject> beats) |
| `Sections` | [`List<SectionObject>`](../../doc/models/section-object.md) | Optional | Sections are defined by large variations in rhythm or timbre, e.g. chorus, verse, bridge, guitar solo, etc. Each section contains its own descriptions of tempo, key, mode, time_signature, and loudness. | List<SectionObject> getSections() | setSections(List<SectionObject> sections) |
| `Segments` | [`List<SegmentObject>`](../../doc/models/segment-object.md) | Optional | Each segment contains a roughly conisistent sound throughout its duration. | List<SegmentObject> getSegments() | setSegments(List<SegmentObject> segments) |
| `Tatums` | [`List<TimeIntervalObject>`](../../doc/models/time-interval-object.md) | Optional | A tatum represents the lowest regular pulse train that a listener intuitively infers from the timing of perceived musical events (segments). | List<TimeIntervalObject> getTatums() | setTatums(List<TimeIntervalObject> tatums) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.models.AudioAnalysisObject;
import com.spotify.api.models.Meta;
import com.spotify.api.models.SectionObject;
import com.spotify.api.models.TimeIntervalObject;
import com.spotify.api.models.Track;
import java.io.IOException;
import java.util.Arrays;

AudioAnalysisObject audioAnalysisObject = new AudioAnalysisObject.Builder()
    .meta(new Meta.Builder()
        .analyzerVersion("analyzer_version8")
        .platform("platform6")
        .detailedStatus("detailed_status8")
        .statusCode(168)
        .timestamp(220L)
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build())
    .track(new Track.Builder()
        .numSamples(156)
        .duration(53.8D)
        .sampleMd5("sample_md56")
        .offsetSeconds(172)
        .windowSeconds(42)
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build())
    .bars(Arrays.asList(
        new TimeIntervalObject.Builder()
            .start(141.7D)
            .duration(145.82D)
            .confidence(1D)
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build(),
        new TimeIntervalObject.Builder()
            .start(141.7D)
            .duration(145.82D)
            .confidence(1D)
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build()
    ))
    .beats(Arrays.asList(
        new TimeIntervalObject.Builder()
            .start(102.56D)
            .duration(106.68D)
            .confidence(1D)
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build(),
        new TimeIntervalObject.Builder()
            .start(102.56D)
            .duration(106.68D)
            .confidence(1D)
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build(),
        new TimeIntervalObject.Builder()
            .start(102.56D)
            .duration(106.68D)
            .confidence(1D)
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build()
    ))
    .sections(Arrays.asList(
        new SectionObject.Builder()
            .start(112.18D)
            .duration(116.3D)
            .confidence(1D)
            .loudness(14.46D)
            .tempo(25D)
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build(),
        new SectionObject.Builder()
            .start(112.18D)
            .duration(116.3D)
            .confidence(1D)
            .loudness(14.46D)
            .tempo(25D)
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build()
    ))
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

