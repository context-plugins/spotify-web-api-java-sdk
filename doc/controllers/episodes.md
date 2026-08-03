# Episodes

```java
EpisodesApi episodesApi = client.getEpisodesApi();
```

## Class Name

`EpisodesApi`

## Methods

* [Get-an-Episode](../../doc/controllers/episodes.md#get-an-episode)
* [Get-Multiple-Episodes](../../doc/controllers/episodes.md#get-multiple-episodes)
* [Get-Users-Saved-Episodes](../../doc/controllers/episodes.md#get-users-saved-episodes)
* [Save-Episodes-User](../../doc/controllers/episodes.md#save-episodes-user)
* [Remove-Episodes-User](../../doc/controllers/episodes.md#remove-episodes-user)
* [Check-Users-Saved-Episodes](../../doc/controllers/episodes.md#check-users-saved-episodes)


# Get-an-Episode

Get Spotify catalog information for a single episode identified by its
unique Spotify ID.

```java
CompletableFuture<ApiResponse<EpisodeObject>> getAnEpisodeAsync(
    final String id,
    final String market)
```

## Authentication

This endpoint requires [oauth_2_0](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `String` | Template, Required | - |
| `market` | `String` | Query, Optional | - |

## Requires scope

### oauth_2_0

`user-read-playback-position`

## Response Type

**200**: An episode

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`EpisodeObject`](../../doc/models/episode-object.md).

## Example Usage

```java
String id = "512ojhOuo1ktJprKbVcKyQ";
String market = "ES";

episodesApi.getAnEpisodeAsync(id, market).thenAccept(result -> {
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


# Get-Multiple-Episodes

Get Spotify catalog information for several episodes based on their Spotify IDs.

```java
CompletableFuture<ApiResponse<ManyEpisodes>> getMultipleEpisodesAsync(
    final String ids,
    final String market)
```

## Authentication

This endpoint requires [oauth_2_0](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `ids` | `String` | Query, Required | - |
| `market` | `String` | Query, Optional | - |

## Requires scope

### oauth_2_0

`user-read-playback-position`

## Response Type

**200**: A set of episodes

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`ManyEpisodes`](../../doc/models/many-episodes.md).

## Example Usage

```java
String ids = "77o6BIVlYM3msb4MMIL1jH,0Q86acNRm6V9GYx55SXKwf";
String market = "ES";

episodesApi.getMultipleEpisodesAsync(ids, market).thenAccept(result -> {
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


# Get-Users-Saved-Episodes

Get a list of the episodes saved in the current Spotify user's library.<br/>
This API endpoint is in __beta__ and could change without warning. Please share any feedback that you have, or issues that you discover, in our [developer community forum](https://community.spotify.com/t5/Spotify-for-Developers/bd-p/Spotify_Developer).

```java
CompletableFuture<ApiResponse<PagingSavedEpisodeObject>> getUsersSavedEpisodesAsync(
    final String market,
    final Integer limit,
    final Integer offset)
```

## Authentication

This endpoint requires [oauth_2_0](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `market` | `String` | Query, Optional | - |
| `limit` | `Integer` | Query, Optional | **Default**: `20`<br><br>**Constraints**: `>= 1`, `<= 50` |
| `offset` | `Integer` | Query, Optional | **Default**: `0` |

## Requires scope

### oauth_2_0

`user-library-read`, `user-read-playback-position`

## Response Type

**200**: Pages of episodes

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`PagingSavedEpisodeObject`](../../doc/models/paging-saved-episode-object.md).

## Example Usage

```java
String market = "ES";
Integer limit = 10;
Integer offset = 5;

episodesApi.getUsersSavedEpisodesAsync(market, limit, offset).thenAccept(result -> {
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


# Save-Episodes-User

Save one or more episodes to the current user's library.<br/>
This API endpoint is in __beta__ and could change without warning. Please share any feedback that you have, or issues that you discover, in our [developer community forum](https://community.spotify.com/t5/Spotify-for-Developers/bd-p/Spotify_Developer).

```java
CompletableFuture<ApiResponse<Void>> saveEpisodesUserAsync(
    final String ids,
    final SaveEpisodesRequest body)
```

## Authentication

This endpoint requires [oauth_2_0](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `ids` | `String` | Query, Required | - |
| `body` | [`SaveEpisodesRequest`](../../doc/models/save-episodes-request.md) | Body, Optional | - |

## Requires scope

### oauth_2_0

`user-library-modify`

## Response Type

**200**: Episode saved

`void`

## Example Usage

```java
String ids = "77o6BIVlYM3msb4MMIL1jH,0Q86acNRm6V9GYx55SXKwf";
episodesApi.saveEpisodesUserAsync(ids, null).thenAccept(result -> {
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


# Remove-Episodes-User

Remove one or more episodes from the current user's library.<br/>
This API endpoint is in __beta__ and could change without warning. Please share any feedback that you have, or issues that you discover, in our [developer community forum](https://community.spotify.com/t5/Spotify-for-Developers/bd-p/Spotify_Developer).

```java
CompletableFuture<ApiResponse<Void>> removeEpisodesUserAsync(
    final String ids,
    final RemoveEpisodesRequest body)
```

## Authentication

This endpoint requires [oauth_2_0](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `ids` | `String` | Query, Required | - |
| `body` | [`RemoveEpisodesRequest`](../../doc/models/remove-episodes-request.md) | Body, Optional | - |

## Requires scope

### oauth_2_0

`user-library-modify`

## Response Type

**200**: Episode removed

`void`

## Example Usage

```java
String ids = "7ouMYWpwJ422jRcDASZB7P,4VqPOruhp5EdPBeR92t6lQ,2takcwOaAZWiXQijPHIx7B";
episodesApi.removeEpisodesUserAsync(ids, null).thenAccept(result -> {
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


# Check-Users-Saved-Episodes

Check if one or more episodes is already saved in the current Spotify user's 'Your Episodes' library.<br/>
This API endpoint is in __beta__ and could change without warning. Please share any feedback that you have, or issues that you discover, in our [developer community forum](https://community.spotify.com/t5/Spotify-for-Developers/bd-p/Spotify_Developer)..

```java
CompletableFuture<ApiResponse<List<Boolean>>> checkUsersSavedEpisodesAsync(
    final String ids)
```

## Authentication

This endpoint requires [oauth_2_0](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `ids` | `String` | Query, Required | - |

## Requires scope

### oauth_2_0

`user-library-read`

## Response Type

**200**: Array of booleans

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type `List<Boolean>`.

## Example Usage

```java
String ids = "77o6BIVlYM3msb4MMIL1jH,0Q86acNRm6V9GYx55SXKwf";

episodesApi.checkUsersSavedEpisodesAsync(ids).thenAccept(result -> {
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

## Example Response

```
[
  false,
  true
]
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Bad or expired token. This can happen if the user revoked a token or<br>the access token has expired. You should re-authenticate the user. | [`Unauthorized1Exception`](../../doc/models/unauthorized-1-exception.md) |
| 403 | Bad OAuth request (wrong consumer key, bad nonce, expired<br>timestamp...). Unfortunately, re-authenticating the user won't help here. | [`Forbidden1Exception`](../../doc/models/forbidden-1-exception.md) |
| 429 | The app has exceeded its rate limits. | [`TooManyRequests1Exception`](../../doc/models/too-many-requests-1-exception.md) |

