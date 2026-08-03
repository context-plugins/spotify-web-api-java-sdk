
# Getting Started with Spotify Web API

## Introduction

You can use Spotify's Web API to discover music and podcasts, manage your Spotify library, control audio playback, and much more. Browse our available Web API endpoints using the sidebar at left, or via the navigation bar on top of this page on smaller screens.

In order to make successful Web API requests your app will need a valid access token. One can be obtained through <a href="https://developer.spotify.com/documentation/general/guides/authorization-guide/">OAuth 2.0</a>.

The base URI for all Web API requests is `https://api.spotify.com/v1`.

Need help? See our <a href="https://developer.spotify.com/documentation/web-api/">Web API</a> for more information, or visit the <a href="https://community.spotify.com/t5/Spotify-for-Developers/bd-p/Spotify_Developer">Spotify for Developers community forum</a> to ask questions and connect with other developers.

## Building

Supported Java version is **8+**.

The generated code uses a few Maven dependencies e.g., Jackson, OkHttp,
and Apache HttpClient. The reference to these dependencies is already
added in the pom.xml file will be installed automatically. Therefore,
you will need internet access for a successful build.

* In order to open the client library in Eclipse click on `File -> Import`.

![Importing SDK into Eclipse - Step 1](https://apidocs.io/illustration/java?workspaceFolder=Spotify%20Web%20API-Java&workspaceName=SpotifyWebApi&projectName=SpotifyWebApiLib&rootNamespace=com.spotify.api&groupId=SpotifyWebApiLib&artifactId=spotify-web-api-lib&version=2024.3.3&step=import0)

* In the import dialog, select `Existing Java Project` and click `Next`.

![Importing SDK into Eclipse - Step 2](https://apidocs.io/illustration/java?workspaceFolder=Spotify%20Web%20API-Java&workspaceName=SpotifyWebApi&projectName=SpotifyWebApiLib&rootNamespace=com.spotify.api&groupId=SpotifyWebApiLib&artifactId=spotify-web-api-lib&version=2024.3.3&step=import1)

* Browse to locate the folder containing the source code. Select the detected location of the project and click `Finish`.

![Importing SDK into Eclipse - Step 3](https://apidocs.io/illustration/java?workspaceFolder=Spotify%20Web%20API-Java&workspaceName=SpotifyWebApi&projectName=SpotifyWebApiLib&rootNamespace=com.spotify.api&groupId=SpotifyWebApiLib&artifactId=spotify-web-api-lib&version=2024.3.3&step=import2)

* Upon successful import, the project will be automatically built by Eclipse after automatically resolving the dependencies.

![Importing SDK into Eclipse - Step 4](https://apidocs.io/illustration/java?workspaceFolder=Spotify%20Web%20API-Java&workspaceName=SpotifyWebApi&projectName=SpotifyWebApiLib&rootNamespace=com.spotify.api&groupId=SpotifyWebApiLib&artifactId=spotify-web-api-lib&version=2024.3.3&step=import3)

* After successfully building the project, the client library needs to be installed as a Maven package in your local cache. Right-click on the project, select `Show in Local Terminal -> Terminal` or use `Ctrl + Alt + T` to open Terminal.

![Importing SDK into Eclipse - Step 5](https://apidocs.io/illustration/java?workspaceFolder=Spotify%20Web%20API-Java&workspaceName=SpotifyWebApi&projectName=SpotifyWebApiLib&rootNamespace=com.spotify.api&groupId=SpotifyWebApiLib&artifactId=spotify-web-api-lib&version=2024.3.3&step=openTerminal)

* In the terminal dialog, run the following command to install client library.

```
mvn install -Dmaven.test.skip=true -Dmaven.javadoc.skip=true
```

![Importing SDK into Eclipse - Step 6](https://apidocs.io/illustration/java?workspaceFolder=Spotify%20Web%20API-Java&workspaceName=SpotifyWebApi&projectName=SpotifyWebApiLib&rootNamespace=com.spotify.api&groupId=SpotifyWebApiLib&artifactId=spotify-web-api-lib&version=2024.3.3&step=installCommand)

## Installation

The following section explains how to use the SpotifyWebApiLib library in a new project.

### 1. Starting a new project

For starting a new project, click the menu command `File > New > Project`.

![Add a new project in Eclipse](https://apidocs.io/illustration/java?workspaceFolder=Spotify%20Web%20API-Java&workspaceName=SpotifyWebApi&projectName=SpotifyWebApiLib&rootNamespace=com.spotify.api&groupId=SpotifyWebApiLib&artifactId=spotify-web-api-lib&version=2024.3.3&step=createNewProject0)

Next, choose `Maven > Maven Project` and click `Next`.

![Create a new Maven Project - Step 1](https://apidocs.io/illustration/java?workspaceFolder=Spotify%20Web%20API-Java&workspaceName=SpotifyWebApi&projectName=SpotifyWebApiLib&rootNamespace=com.spotify.api&groupId=SpotifyWebApiLib&artifactId=spotify-web-api-lib&version=2024.3.3&step=createNewProject1)

Here, make sure to use the current workspace by choosing `Use default Workspace location`, as shown in the picture below and click `Next`.

![Create a new Maven Project - Step 2](https://apidocs.io/illustration/java?workspaceFolder=Spotify%20Web%20API-Java&workspaceName=SpotifyWebApi&projectName=SpotifyWebApiLib&rootNamespace=com.spotify.api&groupId=SpotifyWebApiLib&artifactId=spotify-web-api-lib&version=2024.3.3&step=createNewProject2)

Following this, select the *quick start* project type to create a simple project with an existing class and a `main` method. To do this, choose `maven-archetype-quickstart` item from the list and click `Next`.

![Create a new Maven Project - Step 3](https://apidocs.io/illustration/java?workspaceFolder=Spotify%20Web%20API-Java&workspaceName=SpotifyWebApi&projectName=SpotifyWebApiLib&rootNamespace=com.spotify.api&groupId=SpotifyWebApiLib&artifactId=spotify-web-api-lib&version=2024.3.3&step=createNewProject3)

In the last step, provide a `Group Id` and `Artifact Id` as shown in the picture below and click `Finish`.

![Create a new Maven Project - Step 4](https://apidocs.io/illustration/java?workspaceFolder=Spotify%20Web%20API-Java&workspaceName=SpotifyWebApi&projectName=SpotifyWebApiLib&rootNamespace=com.spotify.api&groupId=SpotifyWebApiLib&artifactId=spotify-web-api-lib&version=2024.3.3&step=createNewProject4)

### 2. Add reference of the library project

The created Maven project manages its dependencies using its `pom.xml` file. In order to add a dependency on the *SpotifyWebApiLib* client library, double click on the `pom.xml` file in the `Package Explorer`. Opening the `pom.xml` file will render a graphical view on the canvas. Here, switch to the `Dependencies` tab and click the `Add` button as shown in the picture below.

![Adding dependency to the client library - Step 1](https://apidocs.io/illustration/java?workspaceFolder=Spotify%20Web%20API-Java&workspaceName=SpotifyWebApi&projectName=SpotifyWebApiLib&rootNamespace=com.spotify.api&groupId=SpotifyWebApiLib&artifactId=spotify-web-api-lib&version=2024.3.3&step=testProject0)

Clicking the `Add` button will open a dialog where you need to specify SpotifyWebApiLib in `Group Id`, spotify-web-api-lib in `Artifact Id` and 2024.3.3 in the `Version` fields. Once added click `OK`. Save the `pom.xml` file.

![Adding dependency to the client library - Step 2](https://apidocs.io/illustration/java?workspaceFolder=Spotify%20Web%20API-Java&workspaceName=SpotifyWebApi&projectName=SpotifyWebApiLib&rootNamespace=com.spotify.api&groupId=SpotifyWebApiLib&artifactId=spotify-web-api-lib&version=2024.3.3&step=testProject1)

![Adding sample code](https://apidocs.io/illustration/java?workspaceFolder=Spotify%20Web%20API-Java&workspaceName=SpotifyWebApi&projectName=SpotifyWebApiLib&rootNamespace=com.spotify.api&groupId=SpotifyWebApiLib&artifactId=spotify-web-api-lib&version=2024.3.3&step=testProject2)

### 3. Write sample code

Once the `SimpleConsoleApp` is created, a file named `App.java` will be visible in the *Package Explorer* with a `main` method. This is the entry point for the execution of the created project.
Here, you can add code to initialize the client library and instantiate a *Controller* class. Sample code to initialize the client library and using controller methods is given in the subsequent sections.

## Initialize the API Client

**_Note:_** Documentation for the client can be found [here.](doc/client.md)

The following parameters are configurable for the API Client:

| Parameter | Type | Description |
|  --- | --- | --- |
| environment | [`Environment`](README.md#environments) | The API environment. <br> **Default: `Environment.PRODUCTION`** |
| httpClientConfig | [`Consumer<HttpClientConfiguration.Builder>`](doc/http-client-configuration-builder.md) | Set up Http Client Configuration instance. |
| loggingConfig | [`Consumer<ApiLoggingConfiguration.Builder>`](doc/api-logging-configuration-builder.md) | Set up Logging Configuration instance. |
| authorizationCodeAuth | [`AuthorizationCodeAuth`](doc/auth/oauth-2-authorization-code-grant.md) | The Credentials Setter for OAuth 2 Authorization Code Grant |

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

## Environments

The SDK can be configured to use a different environment for making API calls. Available environments are:

### Fields

| Name | Description |
|  --- | --- |
| PRODUCTION | **Default** |
| ENVIRONMENT2 | - |

## Authorization

This API uses the following authentication schemes.

* [`oauth_2_0 (OAuth 2 Authorization Code Grant)`](doc/auth/oauth-2-authorization-code-grant.md)

## List of APIs

* [Albums](doc/controllers/albums.md)
* [Artists](doc/controllers/artists.md)
* [Audiobooks](doc/controllers/audiobooks.md)
* [Categories](doc/controllers/categories.md)
* [Chapters](doc/controllers/chapters.md)
* [Episodes](doc/controllers/episodes.md)
* [Genres](doc/controllers/genres.md)
* [Markets](doc/controllers/markets.md)
* [Player](doc/controllers/player.md)
* [Playlists](doc/controllers/playlists.md)
* [Search](doc/controllers/search.md)
* [Shows](doc/controllers/shows.md)
* [Tracks](doc/controllers/tracks.md)
* [Users](doc/controllers/users.md)

## SDK Infrastructure

### Configuration

* [ApiLoggingConfiguration](doc/api-logging-configuration.md)
* [ApiLoggingConfiguration.Builder](doc/api-logging-configuration-builder.md)
* [ApiRequestLoggingConfiguration.Builder](doc/api-request-logging-configuration-builder.md)
* [ApiResponseLoggingConfiguration.Builder](doc/api-response-logging-configuration-builder.md)
* [Configuration Interface](doc/configuration-interface.md)
* [HttpClientConfiguration](doc/http-client-configuration.md)
* [HttpClientConfiguration.Builder](doc/http-client-configuration-builder.md)
* [HttpProxyConfiguration](doc/http-proxy-configuration.md)
* [HttpProxyConfiguration.Builder](doc/http-proxy-configuration-builder.md)

### HTTP

* [Headers](doc/headers.md)
* [HttpCallback Interface](doc/http-callback-interface.md)
* [HttpContext](doc/http-context.md)
* [HttpBodyRequest](doc/http-body-request.md)
* [HttpRequest](doc/http-request.md)
* [HttpResponse](doc/http-response.md)
* [HttpStringResponse](doc/http-string-response.md)

### Utilities

* [ApiException](doc/api-exception.md)
* [ApiResponse](doc/api-response.md)
* [ApiHelper](doc/api-helper.md)
* [FileWrapper](doc/file-wrapper.md)
* [DateTimeHelper](doc/date-time-helper.md)

