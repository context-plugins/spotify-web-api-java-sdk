
# Many Simplified Shows

*This model accepts additional fields of type Object.*

## Structure

`ManySimplifiedShows`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Shows` | [`List<ShowBase>`](../../doc/models/show-base.md) | Required | - | List<ShowBase> getShows() | setShows(List<ShowBase> shows) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.models.CopyrightObject;
import com.spotify.api.models.ExternalUrlObject;
import com.spotify.api.models.ImageObject;
import com.spotify.api.models.ManySimplifiedShows;
import com.spotify.api.models.ShowBase;
import com.spotify.api.models.Type6;
import java.io.IOException;
import java.util.Arrays;

ManySimplifiedShows manySimplifiedShows = new ManySimplifiedShows.Builder(
    Arrays.asList(
        new ShowBase.Builder(
            Arrays.asList(
                "available_markets2"
            ),
            Arrays.asList(
                new CopyrightObject.Builder()
                    .text("text2")
                    .type("type2")
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                    .build()
            ),
            "description8",
            "html_description2",
            false,
            new ExternalUrlObject.Builder()
                .spotify("spotify6")
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build(),
            "href0",
            "id8",
            Arrays.asList(
                new ImageObject.Builder(
                    "https://i.scdn.co/image/ab67616d00001e02ff9ca10b55ce82ae553c8228\n",
                    300,
                    300
                )
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build()
            ),
            false,
            Arrays.asList(
                "languages5"
            ),
            "media_type4",
            "name8",
            "publisher4",
            Type6.SHOW,
            "uri2",
            196
        )
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build()
    )
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

