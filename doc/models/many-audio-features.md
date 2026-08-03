
# Many Audio Features

*This model accepts additional fields of type Object.*

## Structure

`ManyAudioFeatures`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `AudioFeatures` | [`List<AudioFeaturesObject>`](../../doc/models/audio-features-object.md) | Required | - | List<AudioFeaturesObject> getAudioFeatures() | setAudioFeatures(List<AudioFeaturesObject> audioFeatures) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.models.AudioFeaturesObject;
import com.spotify.api.models.ManyAudioFeatures;
import java.io.IOException;
import java.util.Arrays;

ManyAudioFeatures manyAudioFeatures = new ManyAudioFeatures.Builder(
    Arrays.asList(
        new AudioFeaturesObject.Builder()
            .acousticness(0.00242D)
            .analysisUrl("https://api.spotify.com/v1/audio-analysis/2takcwOaAZWiXQijPHIx7B\n")
            .danceability(0.585D)
            .durationMs(237040)
            .energy(0.842D)
            .id("2takcwOaAZWiXQijPHIx7B")
            .instrumentalness(0.00686D)
            .key(9)
            .liveness(0.0866D)
            .loudness(-5.883D)
            .mode(0)
            .speechiness(0.0556D)
            .tempo(118.211D)
            .timeSignature(4)
            .trackHref("https://api.spotify.com/v1/tracks/2takcwOaAZWiXQijPHIx7B\n")
            .uri("spotify:track:2takcwOaAZWiXQijPHIx7B")
            .valence(0.428D)
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build()
    )
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

