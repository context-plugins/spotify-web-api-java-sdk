
# Oauth Token

OAuth 2 Authorization endpoint response

## Structure

`OauthToken`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `AccessToken` | `String` | Required | Access token | String getAccessToken() | setAccessToken(String accessToken) |
| `TokenType` | `String` | Required | Type of access token | String getTokenType() | setTokenType(String tokenType) |
| `ExpiresIn` | `Long` | Optional | Time in seconds before the access token expires | Long getExpiresIn() | setExpiresIn(Long expiresIn) |
| `Scope` | `String` | Optional | List of scopes granted<br>This is a space-delimited list of strings. | String getScope() | setScope(String scope) |
| `Expiry` | `Long` | Optional | Time of token expiry as unix timestamp (UTC) | Long getExpiry() | setExpiry(Long expiry) |
| `RefreshToken` | `String` | Optional | Refresh token<br>Used to get a new access token when it expires. | String getRefreshToken() | setRefreshToken(String refreshToken) |

## Example

```java
import com.spotify.api.models.OauthToken;

OauthToken oauthToken = new OauthToken.Builder(
    "access_token8",
    "token_type8"
)
.expiresIn(10L)
.scope("scope2")
.expiry(152L)
.refreshToken("refresh_token0")
.build();
```

