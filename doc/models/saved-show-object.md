
# Saved Show Object

*This model accepts additional fields of type Object.*

## Structure

`SavedShowObject`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `AddedAt` | `LocalDateTime` | Optional | The date and time the show was saved.<br>Timestamps are returned in ISO 8601 format as Coordinated Universal Time (UTC) with a zero offset: YYYY-MM-DDTHH:MM:SSZ.<br>If the time is imprecise (for example, the date/time of an album release), an additional field indicates the precision; see for example, release_date in an album object. | LocalDateTime getAddedAt() | setAddedAt(LocalDateTime addedAt) |
| `Show` | [`ShowBase`](../../doc/models/show-base.md) | Optional | - | ShowBase getShow() | setShow(ShowBase show) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.DateTimeHelper;
import com.spotify.api.models.CopyrightObject;
import com.spotify.api.models.ExternalUrlObject;
import com.spotify.api.models.ImageObject;
import com.spotify.api.models.SavedShowObject;
import com.spotify.api.models.ShowBase;
import com.spotify.api.models.Type6;
import java.io.IOException;
import java.util.Arrays;

SavedShowObject savedShowObject = new SavedShowObject.Builder()
    .addedAt(DateTimeHelper.fromRfc8601DateTime("2016-03-13T12:52:32.123Z"))
    .show(new ShowBase.Builder(
        Arrays.asList(
            "available_markets0",
            "available_markets1",
            "available_markets2"
        ),
        Arrays.asList(
            new CopyrightObject.Builder()
                .text("text2")
                .type("type2")
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build(),
            new CopyrightObject.Builder()
                .text("text2")
                .type("type2")
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build(),
            new CopyrightObject.Builder()
                .text("text2")
                .type("type2")
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build()
        ),
        "description4",
        "html_description4",
        false,
        new ExternalUrlObject.Builder()
            .spotify("spotify6")
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build(),
        "href8",
        "id6",
        Arrays.asList(
            new ImageObject.Builder(
                "url6",
                182,
                222
            )
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build(),
            new ImageObject.Builder(
                "url6",
                182,
                222
            )
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build(),
            new ImageObject.Builder(
                "url6",
                182,
                222
            )
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build()
        ),
        false,
        Arrays.asList(
            "languages7",
            "languages6",
            "languages5"
        ),
        "media_type6",
        "name6",
        "publisher6",
        Type6.SHOW,
        "uri0",
        198
    )
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build())
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

