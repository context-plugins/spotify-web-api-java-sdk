# Player

```java
PlayerApi playerApi = client.getPlayerApi();
```

## Class Name

`PlayerApi`

## Methods

* [Get-Information-about-the-Users-Current-Playback](../../doc/controllers/player.md#get-information-about-the-users-current-playback)
* [Transfer-a-Users-Playback](../../doc/controllers/player.md#transfer-a-users-playback)
* [Get-a-Users-Available-Devices](../../doc/controllers/player.md#get-a-users-available-devices)
* [Get-the-Users-Currently-Playing-Track](../../doc/controllers/player.md#get-the-users-currently-playing-track)
* [Start-a-Users-Playback](../../doc/controllers/player.md#start-a-users-playback)
* [Pause-a-Users-Playback](../../doc/controllers/player.md#pause-a-users-playback)
* [Skip-Users-Playback-to-Next-Track](../../doc/controllers/player.md#skip-users-playback-to-next-track)
* [Skip-Users-Playback-to-Previous-Track](../../doc/controllers/player.md#skip-users-playback-to-previous-track)
* [Seek-to-Position-in-Currently-Playing-Track](../../doc/controllers/player.md#seek-to-position-in-currently-playing-track)
* [Set-Repeat-Mode-on-Users-Playback](../../doc/controllers/player.md#set-repeat-mode-on-users-playback)
* [Set-Volume-for-Users-Playback](../../doc/controllers/player.md#set-volume-for-users-playback)
* [Toggle-Shuffle-for-Users-Playback](../../doc/controllers/player.md#toggle-shuffle-for-users-playback)
* [Get-Recently-Played](../../doc/controllers/player.md#get-recently-played)
* [Get-Queue](../../doc/controllers/player.md#get-queue)
* [Add-to-Queue](../../doc/controllers/player.md#add-to-queue)


# Get-Information-about-the-Users-Current-Playback

Get information about the user’s current playback state, including track or episode, progress, and active device.

```java
CompletableFuture<ApiResponse<CurrentlyPlayingContextObject>> getInformationAboutTheUsersCurrentPlaybackAsync(
    final String market,
    final String additionalTypes)
```

## Authentication

This endpoint requires [oauth_2_0](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `market` | `String` | Query, Optional | - |
| `additionalTypes` | `String` | Query, Optional | - |

## Requires scope

### oauth_2_0

`user-read-playback-state`

## Response Type

**200**: Information about playback

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`CurrentlyPlayingContextObject`](../../doc/models/currently-playing-context-object.md).

## Example Usage

```java
String market = "ES";

playerApi.getInformationAboutTheUsersCurrentPlaybackAsync(market, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof Unauthorized1Exception) {
        Unauthorized1Exception unauthorized1Exception = (Unauthorized1Exception) cause;
        unauthorized1Exception.printStackTrace();
    } else if (cause instanceof Forbidden1Exception) {
        Forbidden1Exception forbidden1Exception = (Forbidden1Exception) cause;
        forbidden1Exception.printStackTrace();
    } else if (cause instanceof TooManyRequests1Exception) {
        TooManyRequests1Exception tooManyRequests1Exception = (TooManyRequests1Exception) cause;
        tooManyRequests1Exception.printStackTrace();
    } else {
        // fallback for unexpected errors
        exception.printStackTrace();
    }

    return null;
});
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Bad or expired token. This can happen if the user revoked a token or<br>the access token has expired. You should re-authenticate the user. | [`Unauthorized1Exception`](../../doc/models/unauthorized-1-exception.md) |
| 403 | Bad OAuth request (wrong consumer key, bad nonce, expired<br>timestamp...). Unfortunately, re-authenticating the user won't help here. | [`Forbidden1Exception`](../../doc/models/forbidden-1-exception.md) |
| 429 | The app has exceeded its rate limits. | [`TooManyRequests1Exception`](../../doc/models/too-many-requests-1-exception.md) |


# Transfer-a-Users-Playback

Transfer playback to a new device and optionally begin playback. This API only works for users who have Spotify Premium. The order of execution is not guaranteed when you use this API with other Player API endpoints.

```java
CompletableFuture<ApiResponse<Void>> transferAUsersPlaybackAsync(
    final MePlayerRequest body)
```

## Authentication

This endpoint requires [oauth_2_0](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`MePlayerRequest`](../../doc/models/me-player-request.md) | Body, Optional | - |

## Requires scope

### oauth_2_0

`user-modify-playback-state`

## Response Type

**204**: Playback transferred

`void`

## Example Usage

```java
MePlayerRequest body = new MePlayerRequest.Builder(
    Arrays.asList(
        "74ASZWbe4lXaubB36ztrGX"
    )
)
.build();

playerApi.transferAUsersPlaybackAsync(body).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof Unauthorized1Exception) {
        Unauthorized1Exception unauthorized1Exception = (Unauthorized1Exception) cause;
        unauthorized1Exception.printStackTrace();
    } else if (cause instanceof Forbidden1Exception) {
        Forbidden1Exception forbidden1Exception = (Forbidden1Exception) cause;
        forbidden1Exception.printStackTrace();
    } else if (cause instanceof TooManyRequests1Exception) {
        TooManyRequests1Exception tooManyRequests1Exception = (TooManyRequests1Exception) cause;
        tooManyRequests1Exception.printStackTrace();
    } else {
        // fallback for unexpected errors
        exception.printStackTrace();
    }

    return null;
});
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Bad or expired token. This can happen if the user revoked a token or<br>the access token has expired. You should re-authenticate the user. | [`Unauthorized1Exception`](../../doc/models/unauthorized-1-exception.md) |
| 403 | Bad OAuth request (wrong consumer key, bad nonce, expired<br>timestamp...). Unfortunately, re-authenticating the user won't help here. | [`Forbidden1Exception`](../../doc/models/forbidden-1-exception.md) |
| 429 | The app has exceeded its rate limits. | [`TooManyRequests1Exception`](../../doc/models/too-many-requests-1-exception.md) |


# Get-a-Users-Available-Devices

Get information about a user’s available Spotify Connect devices. Some device models are not supported and will not be listed in the API response.

```java
CompletableFuture<ApiResponse<ManyDevices>> getAUsersAvailableDevicesAsync()
```

## Authentication

This endpoint requires [oauth_2_0](../../doc/auth/oauth-2-authorization-code-grant.md)

## Requires scope

### oauth_2_0

`user-read-playback-state`

## Response Type

**200**: A set of devices

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`ManyDevices`](../../doc/models/many-devices.md).

## Example Usage

```java
playerApi.getAUsersAvailableDevicesAsync().thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof Unauthorized1Exception) {
        Unauthorized1Exception unauthorized1Exception = (Unauthorized1Exception) cause;
        unauthorized1Exception.printStackTrace();
    } else if (cause instanceof Forbidden1Exception) {
        Forbidden1Exception forbidden1Exception = (Forbidden1Exception) cause;
        forbidden1Exception.printStackTrace();
    } else if (cause instanceof TooManyRequests1Exception) {
        TooManyRequests1Exception tooManyRequests1Exception = (TooManyRequests1Exception) cause;
        tooManyRequests1Exception.printStackTrace();
    } else {
        // fallback for unexpected errors
        exception.printStackTrace();
    }

    return null;
});
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Bad or expired token. This can happen if the user revoked a token or<br>the access token has expired. You should re-authenticate the user. | [`Unauthorized1Exception`](../../doc/models/unauthorized-1-exception.md) |
| 403 | Bad OAuth request (wrong consumer key, bad nonce, expired<br>timestamp...). Unfortunately, re-authenticating the user won't help here. | [`Forbidden1Exception`](../../doc/models/forbidden-1-exception.md) |
| 429 | The app has exceeded its rate limits. | [`TooManyRequests1Exception`](../../doc/models/too-many-requests-1-exception.md) |


# Get-the-Users-Currently-Playing-Track

Get the object currently being played on the user's Spotify account.

```java
CompletableFuture<ApiResponse<CurrentlyPlayingObject>> getTheUsersCurrentlyPlayingTrackAsync(
    final String market,
    final String additionalTypes)
```

## Authentication

This endpoint requires [oauth_2_0](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `market` | `String` | Query, Optional | - |
| `additionalTypes` | `String` | Query, Optional | - |

## Requires scope

### oauth_2_0

`user-read-currently-playing`

## Response Type

**200**: Information about the currently playing track

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`CurrentlyPlayingObject`](../../doc/models/currently-playing-object.md).

## Example Usage

```java
String market = "ES";

playerApi.getTheUsersCurrentlyPlayingTrackAsync(market, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof Unauthorized1Exception) {
        Unauthorized1Exception unauthorized1Exception = (Unauthorized1Exception) cause;
        unauthorized1Exception.printStackTrace();
    } else if (cause instanceof Forbidden1Exception) {
        Forbidden1Exception forbidden1Exception = (Forbidden1Exception) cause;
        forbidden1Exception.printStackTrace();
    } else if (cause instanceof TooManyRequests1Exception) {
        TooManyRequests1Exception tooManyRequests1Exception = (TooManyRequests1Exception) cause;
        tooManyRequests1Exception.printStackTrace();
    } else {
        // fallback for unexpected errors
        exception.printStackTrace();
    }

    return null;
});
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Bad or expired token. This can happen if the user revoked a token or<br>the access token has expired. You should re-authenticate the user. | [`Unauthorized1Exception`](../../doc/models/unauthorized-1-exception.md) |
| 403 | Bad OAuth request (wrong consumer key, bad nonce, expired<br>timestamp...). Unfortunately, re-authenticating the user won't help here. | [`Forbidden1Exception`](../../doc/models/forbidden-1-exception.md) |
| 429 | The app has exceeded its rate limits. | [`TooManyRequests1Exception`](../../doc/models/too-many-requests-1-exception.md) |


# Start-a-Users-Playback

Start a new context or resume current playback on the user's active device. This API only works for users who have Spotify Premium. The order of execution is not guaranteed when you use this API with other Player API endpoints.

```java
CompletableFuture<ApiResponse<Void>> startAUsersPlaybackAsync(
    final String deviceId,
    final StartOrResumePlaybackRequest body)
```

## Authentication

This endpoint requires [oauth_2_0](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `deviceId` | `String` | Query, Optional | - |
| `body` | [`StartOrResumePlaybackRequest`](../../doc/models/start-or-resume-playback-request.md) | Body, Optional | - |

## Requires scope

### oauth_2_0

`user-modify-playback-state`

## Response Type

**204**: Playback started

`void`

## Example Usage

```java
String deviceId = "0d1841b0976bae2a3a310dd74c0f3df354899bc8";
StartOrResumePlaybackRequest body = new StartOrResumePlaybackRequest.Builder()
    .contextUri("spotify:album:5ht7ItJgpBH7W6vJ5BqpPr")
    .offset(ApiHelper.deserialize("{\"position\":5}"))
    .positionMs(0)
    .build();

playerApi.startAUsersPlaybackAsync(deviceId, body).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof Unauthorized1Exception) {
        Unauthorized1Exception unauthorized1Exception = (Unauthorized1Exception) cause;
        unauthorized1Exception.printStackTrace();
    } else if (cause instanceof Forbidden1Exception) {
        Forbidden1Exception forbidden1Exception = (Forbidden1Exception) cause;
        forbidden1Exception.printStackTrace();
    } else if (cause instanceof TooManyRequests1Exception) {
        TooManyRequests1Exception tooManyRequests1Exception = (TooManyRequests1Exception) cause;
        tooManyRequests1Exception.printStackTrace();
    } else {
        // fallback for unexpected errors
        exception.printStackTrace();
    }

    return null;
});
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Bad or expired token. This can happen if the user revoked a token or<br>the access token has expired. You should re-authenticate the user. | [`Unauthorized1Exception`](../../doc/models/unauthorized-1-exception.md) |
| 403 | Bad OAuth request (wrong consumer key, bad nonce, expired<br>timestamp...). Unfortunately, re-authenticating the user won't help here. | [`Forbidden1Exception`](../../doc/models/forbidden-1-exception.md) |
| 429 | The app has exceeded its rate limits. | [`TooManyRequests1Exception`](../../doc/models/too-many-requests-1-exception.md) |


# Pause-a-Users-Playback

Pause playback on the user's account. This API only works for users who have Spotify Premium. The order of execution is not guaranteed when you use this API with other Player API endpoints.

```java
CompletableFuture<ApiResponse<Void>> pauseAUsersPlaybackAsync(
    final String deviceId)
```

## Authentication

This endpoint requires [oauth_2_0](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `deviceId` | `String` | Query, Optional | - |

## Requires scope

### oauth_2_0

`user-modify-playback-state`

## Response Type

**204**: Playback paused

`void`

## Example Usage

```java
String deviceId = "0d1841b0976bae2a3a310dd74c0f3df354899bc8";

playerApi.pauseAUsersPlaybackAsync(deviceId).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof Unauthorized1Exception) {
        Unauthorized1Exception unauthorized1Exception = (Unauthorized1Exception) cause;
        unauthorized1Exception.printStackTrace();
    } else if (cause instanceof Forbidden1Exception) {
        Forbidden1Exception forbidden1Exception = (Forbidden1Exception) cause;
        forbidden1Exception.printStackTrace();
    } else if (cause instanceof TooManyRequests1Exception) {
        TooManyRequests1Exception tooManyRequests1Exception = (TooManyRequests1Exception) cause;
        tooManyRequests1Exception.printStackTrace();
    } else {
        // fallback for unexpected errors
        exception.printStackTrace();
    }

    return null;
});
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Bad or expired token. This can happen if the user revoked a token or<br>the access token has expired. You should re-authenticate the user. | [`Unauthorized1Exception`](../../doc/models/unauthorized-1-exception.md) |
| 403 | Bad OAuth request (wrong consumer key, bad nonce, expired<br>timestamp...). Unfortunately, re-authenticating the user won't help here. | [`Forbidden1Exception`](../../doc/models/forbidden-1-exception.md) |
| 429 | The app has exceeded its rate limits. | [`TooManyRequests1Exception`](../../doc/models/too-many-requests-1-exception.md) |


# Skip-Users-Playback-to-Next-Track

Skips to next track in the user’s queue. This API only works for users who have Spotify Premium. The order of execution is not guaranteed when you use this API with other Player API endpoints.

```java
CompletableFuture<ApiResponse<Void>> skipUsersPlaybackToNextTrackAsync(
    final String deviceId)
```

## Authentication

This endpoint requires [oauth_2_0](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `deviceId` | `String` | Query, Optional | - |

## Requires scope

### oauth_2_0

`user-modify-playback-state`

## Response Type

**204**: Command sent

`void`

## Example Usage

```java
String deviceId = "0d1841b0976bae2a3a310dd74c0f3df354899bc8";

playerApi.skipUsersPlaybackToNextTrackAsync(deviceId).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof Unauthorized1Exception) {
        Unauthorized1Exception unauthorized1Exception = (Unauthorized1Exception) cause;
        unauthorized1Exception.printStackTrace();
    } else if (cause instanceof Forbidden1Exception) {
        Forbidden1Exception forbidden1Exception = (Forbidden1Exception) cause;
        forbidden1Exception.printStackTrace();
    } else if (cause instanceof TooManyRequests1Exception) {
        TooManyRequests1Exception tooManyRequests1Exception = (TooManyRequests1Exception) cause;
        tooManyRequests1Exception.printStackTrace();
    } else {
        // fallback for unexpected errors
        exception.printStackTrace();
    }

    return null;
});
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Bad or expired token. This can happen if the user revoked a token or<br>the access token has expired. You should re-authenticate the user. | [`Unauthorized1Exception`](../../doc/models/unauthorized-1-exception.md) |
| 403 | Bad OAuth request (wrong consumer key, bad nonce, expired<br>timestamp...). Unfortunately, re-authenticating the user won't help here. | [`Forbidden1Exception`](../../doc/models/forbidden-1-exception.md) |
| 429 | The app has exceeded its rate limits. | [`TooManyRequests1Exception`](../../doc/models/too-many-requests-1-exception.md) |


# Skip-Users-Playback-to-Previous-Track

Skips to previous track in the user’s queue. This API only works for users who have Spotify Premium. The order of execution is not guaranteed when you use this API with other Player API endpoints.

```java
CompletableFuture<ApiResponse<Void>> skipUsersPlaybackToPreviousTrackAsync(
    final String deviceId)
```

## Authentication

This endpoint requires [oauth_2_0](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `deviceId` | `String` | Query, Optional | - |

## Requires scope

### oauth_2_0

`user-modify-playback-state`

## Response Type

**204**: Command sent

`void`

## Example Usage

```java
String deviceId = "0d1841b0976bae2a3a310dd74c0f3df354899bc8";

playerApi.skipUsersPlaybackToPreviousTrackAsync(deviceId).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof Unauthorized1Exception) {
        Unauthorized1Exception unauthorized1Exception = (Unauthorized1Exception) cause;
        unauthorized1Exception.printStackTrace();
    } else if (cause instanceof Forbidden1Exception) {
        Forbidden1Exception forbidden1Exception = (Forbidden1Exception) cause;
        forbidden1Exception.printStackTrace();
    } else if (cause instanceof TooManyRequests1Exception) {
        TooManyRequests1Exception tooManyRequests1Exception = (TooManyRequests1Exception) cause;
        tooManyRequests1Exception.printStackTrace();
    } else {
        // fallback for unexpected errors
        exception.printStackTrace();
    }

    return null;
});
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Bad or expired token. This can happen if the user revoked a token or<br>the access token has expired. You should re-authenticate the user. | [`Unauthorized1Exception`](../../doc/models/unauthorized-1-exception.md) |
| 403 | Bad OAuth request (wrong consumer key, bad nonce, expired<br>timestamp...). Unfortunately, re-authenticating the user won't help here. | [`Forbidden1Exception`](../../doc/models/forbidden-1-exception.md) |
| 429 | The app has exceeded its rate limits. | [`TooManyRequests1Exception`](../../doc/models/too-many-requests-1-exception.md) |


# Seek-to-Position-in-Currently-Playing-Track

Seeks to the given position in the user’s currently playing track. This API only works for users who have Spotify Premium. The order of execution is not guaranteed when you use this API with other Player API endpoints.

```java
CompletableFuture<ApiResponse<Void>> seekToPositionInCurrentlyPlayingTrackAsync(
    final int positionMs,
    final String deviceId)
```

## Authentication

This endpoint requires [oauth_2_0](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `positionMs` | `int` | Query, Required | - |
| `deviceId` | `String` | Query, Optional | - |

## Requires scope

### oauth_2_0

`user-modify-playback-state`

## Response Type

**204**: Command sent

`void`

## Example Usage

```java
int positionMs = 25000;
String deviceId = "0d1841b0976bae2a3a310dd74c0f3df354899bc8";

playerApi.seekToPositionInCurrentlyPlayingTrackAsync(positionMs, deviceId).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof Unauthorized1Exception) {
        Unauthorized1Exception unauthorized1Exception = (Unauthorized1Exception) cause;
        unauthorized1Exception.printStackTrace();
    } else if (cause instanceof Forbidden1Exception) {
        Forbidden1Exception forbidden1Exception = (Forbidden1Exception) cause;
        forbidden1Exception.printStackTrace();
    } else if (cause instanceof TooManyRequests1Exception) {
        TooManyRequests1Exception tooManyRequests1Exception = (TooManyRequests1Exception) cause;
        tooManyRequests1Exception.printStackTrace();
    } else {
        // fallback for unexpected errors
        exception.printStackTrace();
    }

    return null;
});
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Bad or expired token. This can happen if the user revoked a token or<br>the access token has expired. You should re-authenticate the user. | [`Unauthorized1Exception`](../../doc/models/unauthorized-1-exception.md) |
| 403 | Bad OAuth request (wrong consumer key, bad nonce, expired<br>timestamp...). Unfortunately, re-authenticating the user won't help here. | [`Forbidden1Exception`](../../doc/models/forbidden-1-exception.md) |
| 429 | The app has exceeded its rate limits. | [`TooManyRequests1Exception`](../../doc/models/too-many-requests-1-exception.md) |


# Set-Repeat-Mode-on-Users-Playback

Set the repeat mode for the user's playback. This API only works for users who have Spotify Premium. The order of execution is not guaranteed when you use this API with other Player API endpoints.

```java
CompletableFuture<ApiResponse<Void>> setRepeatModeOnUsersPlaybackAsync(
    final String state,
    final String deviceId)
```

## Authentication

This endpoint requires [oauth_2_0](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `state` | `String` | Query, Required | - |
| `deviceId` | `String` | Query, Optional | - |

## Requires scope

### oauth_2_0

`user-modify-playback-state`

## Response Type

**204**: Command sent

`void`

## Example Usage

```java
String state = "context";
String deviceId = "0d1841b0976bae2a3a310dd74c0f3df354899bc8";

playerApi.setRepeatModeOnUsersPlaybackAsync(state, deviceId).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof Unauthorized1Exception) {
        Unauthorized1Exception unauthorized1Exception = (Unauthorized1Exception) cause;
        unauthorized1Exception.printStackTrace();
    } else if (cause instanceof Forbidden1Exception) {
        Forbidden1Exception forbidden1Exception = (Forbidden1Exception) cause;
        forbidden1Exception.printStackTrace();
    } else if (cause instanceof TooManyRequests1Exception) {
        TooManyRequests1Exception tooManyRequests1Exception = (TooManyRequests1Exception) cause;
        tooManyRequests1Exception.printStackTrace();
    } else {
        // fallback for unexpected errors
        exception.printStackTrace();
    }

    return null;
});
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Bad or expired token. This can happen if the user revoked a token or<br>the access token has expired. You should re-authenticate the user. | [`Unauthorized1Exception`](../../doc/models/unauthorized-1-exception.md) |
| 403 | Bad OAuth request (wrong consumer key, bad nonce, expired<br>timestamp...). Unfortunately, re-authenticating the user won't help here. | [`Forbidden1Exception`](../../doc/models/forbidden-1-exception.md) |
| 429 | The app has exceeded its rate limits. | [`TooManyRequests1Exception`](../../doc/models/too-many-requests-1-exception.md) |


# Set-Volume-for-Users-Playback

Set the volume for the user’s current playback device. This API only works for users who have Spotify Premium. The order of execution is not guaranteed when you use this API with other Player API endpoints.

```java
CompletableFuture<ApiResponse<Void>> setVolumeForUsersPlaybackAsync(
    final int volumePercent,
    final String deviceId)
```

## Authentication

This endpoint requires [oauth_2_0](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `volumePercent` | `int` | Query, Required | - |
| `deviceId` | `String` | Query, Optional | - |

## Requires scope

### oauth_2_0

`user-modify-playback-state`

## Response Type

**204**: Command sent

`void`

## Example Usage

```java
int volumePercent = 50;
String deviceId = "0d1841b0976bae2a3a310dd74c0f3df354899bc8";

playerApi.setVolumeForUsersPlaybackAsync(volumePercent, deviceId).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof Unauthorized1Exception) {
        Unauthorized1Exception unauthorized1Exception = (Unauthorized1Exception) cause;
        unauthorized1Exception.printStackTrace();
    } else if (cause instanceof Forbidden1Exception) {
        Forbidden1Exception forbidden1Exception = (Forbidden1Exception) cause;
        forbidden1Exception.printStackTrace();
    } else if (cause instanceof TooManyRequests1Exception) {
        TooManyRequests1Exception tooManyRequests1Exception = (TooManyRequests1Exception) cause;
        tooManyRequests1Exception.printStackTrace();
    } else {
        // fallback for unexpected errors
        exception.printStackTrace();
    }

    return null;
});
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Bad or expired token. This can happen if the user revoked a token or<br>the access token has expired. You should re-authenticate the user. | [`Unauthorized1Exception`](../../doc/models/unauthorized-1-exception.md) |
| 403 | Bad OAuth request (wrong consumer key, bad nonce, expired<br>timestamp...). Unfortunately, re-authenticating the user won't help here. | [`Forbidden1Exception`](../../doc/models/forbidden-1-exception.md) |
| 429 | The app has exceeded its rate limits. | [`TooManyRequests1Exception`](../../doc/models/too-many-requests-1-exception.md) |


# Toggle-Shuffle-for-Users-Playback

Toggle shuffle on or off for user’s playback. This API only works for users who have Spotify Premium. The order of execution is not guaranteed when you use this API with other Player API endpoints.

```java
CompletableFuture<ApiResponse<Void>> toggleShuffleForUsersPlaybackAsync(
    final boolean state,
    final String deviceId)
```

## Authentication

This endpoint requires [oauth_2_0](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `state` | `boolean` | Query, Required | - |
| `deviceId` | `String` | Query, Optional | - |

## Requires scope

### oauth_2_0

`user-modify-playback-state`

## Response Type

**204**: Command sent

`void`

## Example Usage

```java
boolean state = true;
String deviceId = "0d1841b0976bae2a3a310dd74c0f3df354899bc8";

playerApi.toggleShuffleForUsersPlaybackAsync(state, deviceId).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof Unauthorized1Exception) {
        Unauthorized1Exception unauthorized1Exception = (Unauthorized1Exception) cause;
        unauthorized1Exception.printStackTrace();
    } else if (cause instanceof Forbidden1Exception) {
        Forbidden1Exception forbidden1Exception = (Forbidden1Exception) cause;
        forbidden1Exception.printStackTrace();
    } else if (cause instanceof TooManyRequests1Exception) {
        TooManyRequests1Exception tooManyRequests1Exception = (TooManyRequests1Exception) cause;
        tooManyRequests1Exception.printStackTrace();
    } else {
        // fallback for unexpected errors
        exception.printStackTrace();
    }

    return null;
});
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Bad or expired token. This can happen if the user revoked a token or<br>the access token has expired. You should re-authenticate the user. | [`Unauthorized1Exception`](../../doc/models/unauthorized-1-exception.md) |
| 403 | Bad OAuth request (wrong consumer key, bad nonce, expired<br>timestamp...). Unfortunately, re-authenticating the user won't help here. | [`Forbidden1Exception`](../../doc/models/forbidden-1-exception.md) |
| 429 | The app has exceeded its rate limits. | [`TooManyRequests1Exception`](../../doc/models/too-many-requests-1-exception.md) |


# Get-Recently-Played

Get tracks from the current user's recently played tracks.
_**Note**: Currently doesn't support podcast episodes._

```java
CompletableFuture<ApiResponse<CursorPagingPlayHistoryObject>> getRecentlyPlayedAsync(
    final Integer limit,
    final Long after,
    final Integer before)
```

## Authentication

This endpoint requires [oauth_2_0](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `limit` | `Integer` | Query, Optional | **Default**: `20`<br><br>**Constraints**: `>= 1`, `<= 50` |
| `after` | `Long` | Query, Optional | - |
| `before` | `Integer` | Query, Optional | - |

## Requires scope

### oauth_2_0

`user-read-recently-played`

## Response Type

**200**: A paged set of tracks

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`CursorPagingPlayHistoryObject`](../../doc/models/cursor-paging-play-history-object.md).

## Example Usage

```java
Integer limit = 10;
Long after = 1484811043508L;

playerApi.getRecentlyPlayedAsync(limit, after, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof Unauthorized1Exception) {
        Unauthorized1Exception unauthorized1Exception = (Unauthorized1Exception) cause;
        unauthorized1Exception.printStackTrace();
    } else if (cause instanceof Forbidden1Exception) {
        Forbidden1Exception forbidden1Exception = (Forbidden1Exception) cause;
        forbidden1Exception.printStackTrace();
    } else if (cause instanceof TooManyRequests1Exception) {
        TooManyRequests1Exception tooManyRequests1Exception = (TooManyRequests1Exception) cause;
        tooManyRequests1Exception.printStackTrace();
    } else {
        // fallback for unexpected errors
        exception.printStackTrace();
    }

    return null;
});
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Bad or expired token. This can happen if the user revoked a token or<br>the access token has expired. You should re-authenticate the user. | [`Unauthorized1Exception`](../../doc/models/unauthorized-1-exception.md) |
| 403 | Bad OAuth request (wrong consumer key, bad nonce, expired<br>timestamp...). Unfortunately, re-authenticating the user won't help here. | [`Forbidden1Exception`](../../doc/models/forbidden-1-exception.md) |
| 429 | The app has exceeded its rate limits. | [`TooManyRequests1Exception`](../../doc/models/too-many-requests-1-exception.md) |


# Get-Queue

Get the list of objects that make up the user's queue.

```java
CompletableFuture<ApiResponse<QueueObject>> getQueueAsync()
```

## Authentication

This endpoint requires [oauth_2_0](../../doc/auth/oauth-2-authorization-code-grant.md)

## Requires scope

### oauth_2_0

`user-read-currently-playing`, `user-read-playback-state`

## Response Type

**200**: Information about the queue

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`QueueObject`](../../doc/models/queue-object.md).

## Example Usage

```java
playerApi.getQueueAsync().thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof Unauthorized1Exception) {
        Unauthorized1Exception unauthorized1Exception = (Unauthorized1Exception) cause;
        unauthorized1Exception.printStackTrace();
    } else if (cause instanceof Forbidden1Exception) {
        Forbidden1Exception forbidden1Exception = (Forbidden1Exception) cause;
        forbidden1Exception.printStackTrace();
    } else if (cause instanceof TooManyRequests1Exception) {
        TooManyRequests1Exception tooManyRequests1Exception = (TooManyRequests1Exception) cause;
        tooManyRequests1Exception.printStackTrace();
    } else {
        // fallback for unexpected errors
        exception.printStackTrace();
    }

    return null;
});
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Bad or expired token. This can happen if the user revoked a token or<br>the access token has expired. You should re-authenticate the user. | [`Unauthorized1Exception`](../../doc/models/unauthorized-1-exception.md) |
| 403 | Bad OAuth request (wrong consumer key, bad nonce, expired<br>timestamp...). Unfortunately, re-authenticating the user won't help here. | [`Forbidden1Exception`](../../doc/models/forbidden-1-exception.md) |
| 429 | The app has exceeded its rate limits. | [`TooManyRequests1Exception`](../../doc/models/too-many-requests-1-exception.md) |


# Add-to-Queue

Add an item to the end of the user's current playback queue. This API only works for users who have Spotify Premium. The order of execution is not guaranteed when you use this API with other Player API endpoints.

```java
CompletableFuture<ApiResponse<Void>> addToQueueAsync(
    final String uri,
    final String deviceId)
```

## Authentication

This endpoint requires [oauth_2_0](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `uri` | `String` | Query, Required | - |
| `deviceId` | `String` | Query, Optional | - |

## Requires scope

### oauth_2_0

`user-modify-playback-state`

## Response Type

**204**: Command received

`void`

## Example Usage

```java
String uri = "spotify:track:4iV5W9uYEdYUVa79Axb7Rh";
String deviceId = "0d1841b0976bae2a3a310dd74c0f3df354899bc8";

playerApi.addToQueueAsync(uri, deviceId).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof Unauthorized1Exception) {
        Unauthorized1Exception unauthorized1Exception = (Unauthorized1Exception) cause;
        unauthorized1Exception.printStackTrace();
    } else if (cause instanceof Forbidden1Exception) {
        Forbidden1Exception forbidden1Exception = (Forbidden1Exception) cause;
        forbidden1Exception.printStackTrace();
    } else if (cause instanceof TooManyRequests1Exception) {
        TooManyRequests1Exception tooManyRequests1Exception = (TooManyRequests1Exception) cause;
        tooManyRequests1Exception.printStackTrace();
    } else {
        // fallback for unexpected errors
        exception.printStackTrace();
    }

    return null;
});
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Bad or expired token. This can happen if the user revoked a token or<br>the access token has expired. You should re-authenticate the user. | [`Unauthorized1Exception`](../../doc/models/unauthorized-1-exception.md) |
| 403 | Bad OAuth request (wrong consumer key, bad nonce, expired<br>timestamp...). Unfortunately, re-authenticating the user won't help here. | [`Forbidden1Exception`](../../doc/models/forbidden-1-exception.md) |
| 429 | The app has exceeded its rate limits. | [`TooManyRequests1Exception`](../../doc/models/too-many-requests-1-exception.md) |

