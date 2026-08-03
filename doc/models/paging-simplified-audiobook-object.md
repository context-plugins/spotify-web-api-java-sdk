
# Paging Simplified Audiobook Object

*This model accepts additional fields of type Object.*

## Structure

`PagingSimplifiedAudiobookObject`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Href` | `String` | Required | A link to the Web API endpoint returning the full result of the request | String getHref() | setHref(String href) |
| `Limit` | `int` | Required | The maximum number of items in the response (as set in the query or by default). | int getLimit() | setLimit(int limit) |
| `Next` | `String` | Required | URL to the next page of items. ( `null` if none) | String getNext() | setNext(String next) |
| `Offset` | `int` | Required | The offset of the items returned (as set in the query or by default) | int getOffset() | setOffset(int offset) |
| `Previous` | `String` | Required | URL to the previous page of items. ( `null` if none) | String getPrevious() | setPrevious(String previous) |
| `Total` | `int` | Required | The total number of items available to return. | int getTotal() | setTotal(int total) |
| `Items` | [`List<AudiobookBase>`](../../doc/models/audiobook-base.md) | Required | - | List<AudiobookBase> getItems() | setItems(List<AudiobookBase> items) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.models.AudiobookBase;
import com.spotify.api.models.AuthorObject;
import com.spotify.api.models.CopyrightObject;
import com.spotify.api.models.ExternalUrlObject;
import com.spotify.api.models.ImageObject;
import com.spotify.api.models.NarratorObject;
import com.spotify.api.models.PagingSimplifiedAudiobookObject;
import com.spotify.api.models.Type9;
import java.io.IOException;
import java.util.Arrays;

PagingSimplifiedAudiobookObject pagingSimplifiedAudiobookObject = new PagingSimplifiedAudiobookObject.Builder(
    "https://api.spotify.com/v1/me/shows?offset=0&limit=20\n",
    20,
    "https://api.spotify.com/v1/me/shows?offset=1&limit=1",
    0,
    "https://api.spotify.com/v1/me/shows?offset=1&limit=1",
    4,
    Arrays.asList(
        new AudiobookBase.Builder(
            Arrays.asList(
                new AuthorObject.Builder()
                    .name("name0")
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                    .build()
            ),
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
            "description2",
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
            Arrays.asList(
                "languages5"
            ),
            "media_type4",
            "name8",
            Arrays.asList(
                new NarratorObject.Builder()
                    .name("name0")
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                    .build()
            ),
            "publisher4",
            Type9.AUDIOBOOK,
            "uri2",
            202
        )
        .edition("Unabridged")
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build()
    )
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

