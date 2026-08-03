
# External Id Object

*This model accepts additional fields of type Object.*

## Structure

`ExternalIdObject`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Isrc` | `String` | Optional | [International Standard Recording Code](http://en.wikipedia.org/wiki/International_Standard_Recording_Code) | String getIsrc() | setIsrc(String isrc) |
| `Ean` | `String` | Optional | [International Article Number](http://en.wikipedia.org/wiki/International_Article_Number_%28EAN%29) | String getEan() | setEan(String ean) |
| `Upc` | `String` | Optional | [Universal Product Code](http://en.wikipedia.org/wiki/Universal_Product_Code) | String getUpc() | setUpc(String upc) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.spotify.api.ApiHelper;
import com.spotify.api.models.ExternalIdObject;
import java.io.IOException;

ExternalIdObject externalIdObject = new ExternalIdObject.Builder()
    .isrc("isrc4")
    .ean("ean2")
    .upc("upc6")
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

