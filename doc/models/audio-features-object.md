
# Audio Features Object

*This model accepts additional fields of type Object.*

## Structure

`AudioFeaturesObject`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Acousticness` | `Double` | Optional | A confidence measure from 0.0 to 1.0 of whether the track is acoustic. 1.0 represents high confidence the track is acoustic.<br><br>**Constraints**: `>= 0`, `<= 1` | Double getAcousticness() | setAcousticness(Double acousticness) |
| `AnalysisUrl` | `String` | Optional | A URL to access the full audio analysis of this track. An access token is required to access this data. | String getAnalysisUrl() | setAnalysisUrl(String analysisUrl) |
| `Danceability` | `Double` | Optional | Danceability describes how suitable a track is for dancing based on a combination of musical elements including tempo, rhythm stability, beat strength, and overall regularity. A value of 0.0 is least danceable and 1.0 is most danceable. | Double getDanceability() | setDanceability(Double danceability) |
| `DurationMs` | `Integer` | Optional | The duration of the track in milliseconds. | Integer getDurationMs() | setDurationMs(Integer durationMs) |
| `Energy` | `Double` | Optional | Energy is a measure from 0.0 to 1.0 and represents a perceptual measure of intensity and activity. Typically, energetic tracks feel fast, loud, and noisy. For example, death metal has high energy, while a Bach prelude scores low on the scale. Perceptual features contributing to this attribute include dynamic range, perceived loudness, timbre, onset rate, and general entropy. | Double getEnergy() | setEnergy(Double energy) |
| `Id` | `String` | Optional | The Spotify ID for the track. | String getId() | setId(String id) |
| `Instrumentalness` | `Double` | Optional | Predicts whether a track contains no vocals. "Ooh" and "aah" sounds are treated as instrumental in this context. Rap or spoken word tracks are clearly "vocal". The closer the instrumentalness value is to 1.0, the greater likelihood the track contains no vocal content. Values above 0.5 are intended to represent instrumental tracks, but confidence is higher as the value approaches 1.0. | Double getInstrumentalness() | setInstrumentalness(Double instrumentalness) |
| `Key` | `Integer` | Optional | The key the track is in. Integers map to pitches using standard [Pitch Class notation](https://en.wikipedia.org/wiki/Pitch_class). E.g. 0 = C, 1 = C♯/D♭, 2 = D, and so on. If no key was detected, the value is -1.<br><br>**Constraints**: `>= -1`, `<= 11` | Integer getKey() | setKey(Integer key) |
| `Liveness` | `Double` | Optional | Detects the presence of an audience in the recording. Higher liveness values represent an increased probability that the track was performed live. A value above 0.8 provides strong likelihood that the track is live. | Double getLiveness() | setLiveness(Double liveness) |
| `Loudness` | `Double` | Optional | The overall loudness of a track in decibels (dB). Loudness values are averaged across the entire track and are useful for comparing relative loudness of tracks. Loudness is the quality of a sound that is the primary psychological correlate of physical strength (amplitude). Values typically range between -60 and 0 db. | Double getLoudness() | setLoudness(Double loudness) |
| `Mode` | `Integer` | Optional | Mode indicates the modality (major or minor) of a track, the type of scale from which its melodic content is derived. Major is represented by 1 and minor is 0. | Integer getMode() | setMode(Integer mode) |
| `Speechiness` | `Double` | Optional | Speechiness detects the presence of spoken words in a track. The more exclusively speech-like the recording (e.g. talk show, audio book, poetry), the closer to 1.0 the attribute value. Values above 0.66 describe tracks that are probably made entirely of spoken words. Values between 0.33 and 0.66 describe tracks that may contain both music and speech, either in sections or layered, including such cases as rap music. Values below 0.33 most likely represent music and other non-speech-like tracks. | Double getSpeechiness() | setSpeechiness(Double speechiness) |
| `Tempo` | `Double` | Optional | The overall estimated tempo of a track in beats per minute (BPM). In musical terminology, tempo is the speed or pace of a given piece and derives directly from the average beat duration. | Double getTempo() | setTempo(Double tempo) |
| `TimeSignature` | `Integer` | Optional | An estimated time signature. The time signature (meter) is a notational convention to specify how many beats are in each bar (or measure). The time signature ranges from 3 to 7 indicating time signatures of "3/4", to "7/4".<br><br>**Constraints**: `>= 3`, `<= 7` | Integer getTimeSignature() | setTimeSignature(Integer timeSignature) |
| `TrackHref` | `String` | Optional | A link to the Web API endpoint providing full details of the track. | String getTrackHref() | setTrackHref(String trackHref) |
| `Type` | [`Type8`](../../doc/models/type-8.md) | Optional | - | Type8 getType() | setType(Type8 type) |
| `Uri` | `String` | Optional | The Spotify URI for the track. | String getUri() | setUri(String uri) |
| `Valence` | `Double` | Optional | A measure from 0.0 to 1.0 describing the musical positiveness conveyed by a track. Tracks with high valence sound more positive (e.g. happy, cheerful, euphoric), while tracks with low valence sound more negative (e.g. sad, depressed, angry).<br><br>**Constraints**: `>= 0`, `<= 1` | Double getValence() | setValence(Double valence) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.models.AudioFeaturesObject;
import java.io.IOException;

AudioFeaturesObject audioFeaturesObject = new AudioFeaturesObject.Builder()
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
    .build();
```

