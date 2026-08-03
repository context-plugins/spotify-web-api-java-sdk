
# Client Class Documentation

The following parameters are configurable for the API Client:

| Parameter | Type | Description |
|  --- | --- | --- |
| environment | [`Environment`](../README.md#environments) | The API environment. <br> **Default: `Environment.PRODUCTION`** |
| httpClientConfig | [`Consumer<HttpClientConfiguration.Builder>`](../doc/http-client-configuration-builder.md) | Set up Http Client Configuration instance. |
| loggingConfig | [`Consumer<ApiLoggingConfiguration.Builder>`](../doc/api-logging-configuration-builder.md) | Set up Logging Configuration instance. |
| authorizationCodeAuth | [`AuthorizationCodeAuth`](auth/oauth-2-authorization-code-grant.md) | The Credentials Setter for OAuth 2 Authorization Code Grant |

The API client can be initialized as follows:

```java
import com.spotify.api.Environment;
import com.spotify.api.SpotifyWebApiClient;
import com.spotify.api.authentication.AuthorizationCodeAuthModel;
import com.spotify.api.exceptions.ApiException;
import com.spotify.api.http.response.ApiResponse;
import com.spotify.api.models.OauthScope;
import com.spotify.api.models.OauthToken;
import java.io.IOException;
import java.util.Arrays;
import org.slf4j.event.Level;

public class Program {
    public static void main(String[] args) {
        SpotifyWebApiClient client = new SpotifyWebApiClient.Builder()
            .loggingConfig(builder -> builder
                    .level(Level.DEBUG)
                    .requestConfig(logConfigBuilder -> logConfigBuilder.body(true))
                    .responseConfig(logConfigBuilder -> logConfigBuilder.headers(true)))
            .httpClientConfig(configBuilder -> configBuilder
                    .timeout(0))
            .authorizationCodeAuth(new AuthorizationCodeAuthModel.Builder(
                    "OAuthClientId",
                    "OAuthClientSecret",
                    "OAuthRedirectUri"
                )
                .oauthScopes(Arrays.asList(
                        OauthScope.APP_REMOTE_CONTROL,
                        OauthScope.PLAYLIST_READ_PRIVATE
                    ))
                .build())
            .environment(Environment.PRODUCTION)
            .build();

    }
}
```

## Spotify Web APIClient Class

The gateway for the SDK. This class acts as a factory for the Apis and also holds the configuration of the SDK.

### Apis

| Name | Description | Return Type |
|  --- | --- | --- |
| `getAlbumsApi()` | Provides access to Albums controller. | `AlbumsApi` |
| `getArtistsApi()` | Provides access to Artists controller. | `ArtistsApi` |
| `getAudiobooksApi()` | Provides access to Audiobooks controller. | `AudiobooksApi` |
| `getCategoriesApi()` | Provides access to Categories controller. | `CategoriesApi` |
| `getChaptersApi()` | Provides access to Chapters controller. | `ChaptersApi` |
| `getEpisodesApi()` | Provides access to Episodes controller. | `EpisodesApi` |
| `getGenresApi()` | Provides access to Genres controller. | `GenresApi` |
| `getMarketsApi()` | Provides access to Markets controller. | `MarketsApi` |
| `getPlayerApi()` | Provides access to Player controller. | `PlayerApi` |
| `getPlaylistsApi()` | Provides access to Playlists controller. | `PlaylistsApi` |
| `getSearchApi()` | Provides access to Search controller. | `SearchApi` |
| `getShowsApi()` | Provides access to Shows controller. | `ShowsApi` |
| `getTracksApi()` | Provides access to Tracks controller. | `TracksApi` |
| `getUsersApi()` | Provides access to Users controller. | `UsersApi` |
| `getOauthAuthorizationApi()` | Provides access to OauthAuthorization controller. | `OauthAuthorizationApi` |

### Methods

| Name | Description | Return Type |
|  --- | --- | --- |
| `shutdown()` | Shutdown the underlying HttpClient instance. | `void` |
| `getEnvironment()` | Current API environment. | `Environment` |
| `getHttpClient()` | The HTTP Client instance to use for making HTTP requests. | `HttpClient` |
| `getHttpClientConfig()` | Http Client Configuration instance. | [`ReadonlyHttpClientConfiguration`](../doc/http-client-configuration.md) |
| `getLoggingConfig()` | Logging Configuration instance. | [`ReadonlyLoggingConfiguration`](../doc/api-logging-configuration.md) |
| `getAuthorizationCodeAuth()` | The credentials to use with AuthorizationCodeAuth. | [`AuthorizationCodeAuth`](auth/oauth-2-authorization-code-grant.md) |
| `getBaseUri(Server server)` | Get base URI by current environment | `String` |
| `getBaseUri()` | Get base URI by current environment | `String` |

