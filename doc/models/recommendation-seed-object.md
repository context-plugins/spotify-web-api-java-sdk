
# Recommendation Seed Object

*This model accepts additional fields of type Object.*

## Structure

`RecommendationSeedObject`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `AfterFilteringSize` | `Integer` | Optional | The number of tracks available after min\_\* and max\_\* filters have been applied. | Integer getAfterFilteringSize() | setAfterFilteringSize(Integer afterFilteringSize) |
| `AfterRelinkingSize` | `Integer` | Optional | The number of tracks available after relinking for regional availability. | Integer getAfterRelinkingSize() | setAfterRelinkingSize(Integer afterRelinkingSize) |
| `Href` | `String` | Optional | A link to the full track or artist data for this seed. For tracks this will be a link to a Track Object. For artists a link to an Artist Object. For genre seeds, this value will be `null`. | String getHref() | setHref(String href) |
| `Id` | `String` | Optional | The id used to select this seed. This will be the same as the string used in the `seed_artists`, `seed_tracks` or `seed_genres` parameter. | String getId() | setId(String id) |
| `InitialPoolSize` | `Integer` | Optional | The number of recommended tracks available for this seed. | Integer getInitialPoolSize() | setInitialPoolSize(Integer initialPoolSize) |
| `Type` | `String` | Optional | The entity type of this seed. One of `artist`, `track` or `genre`. | String getType() | setType(String type) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.models.RecommendationSeedObject;
import java.io.IOException;

RecommendationSeedObject recommendationSeedObject = new RecommendationSeedObject.Builder()
    .afterFilteringSize(118)
    .afterRelinkingSize(194)
    .href("href0")
    .id("id8")
    .initialPoolSize(124)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

