
# Paged Categories

*This model accepts additional fields of type Object.*

## Structure

`PagedCategories`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Categories` | [`Categories`](../../doc/models/categories.md) | Required | - | Categories getCategories() | setCategories(Categories categories) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.models.Categories;
import com.spotify.api.models.CategoryObject;
import com.spotify.api.models.ImageObject;
import com.spotify.api.models.PagedCategories;
import java.io.IOException;
import java.util.Arrays;

PagedCategories pagedCategories = new PagedCategories.Builder(
    new Categories.Builder(
        "https://api.spotify.com/v1/me/shows?offset=0&limit=20\n",
        20,
        "https://api.spotify.com/v1/me/shows?offset=1&limit=1",
        0,
        "https://api.spotify.com/v1/me/shows?offset=1&limit=1",
        4,
        Arrays.asList(
            new CategoryObject.Builder(
                "href0",
                Arrays.asList(
                    new ImageObject.Builder(
                        "https://i.scdn.co/image/ab67616d00001e02ff9ca10b55ce82ae553c8228\n",
                        300,
                        300
                    )
                    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                    .build()
                ),
                "equal",
                "EQUAL"
            )
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build()
        )
    )
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build()
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

