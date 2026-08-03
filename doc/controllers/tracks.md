# Tracks

```java
TracksApi tracksApi = client.getTracksApi();
```

## Class Name

`TracksApi`

## Methods

* [Get-Track](../../doc/controllers/tracks.md#get-track)
* [Get-Several-Tracks](../../doc/controllers/tracks.md#get-several-tracks)
* [Get-Users-Saved-Tracks](../../doc/controllers/tracks.md#get-users-saved-tracks)
* [Save-Tracks-User](../../doc/controllers/tracks.md#save-tracks-user)
* [Remove-Tracks-User](../../doc/controllers/tracks.md#remove-tracks-user)
* [Check-Users-Saved-Tracks](../../doc/controllers/tracks.md#check-users-saved-tracks)
* [Get-Several-Audio-Features](../../doc/controllers/tracks.md#get-several-audio-features)
* [Get-Audio-Features](../../doc/controllers/tracks.md#get-audio-features)
* [Get-Audio-Analysis](../../doc/controllers/tracks.md#get-audio-analysis)
* [Get-Recommendations](../../doc/controllers/tracks.md#get-recommendations)


# Get-Track

Get Spotify catalog information for a single track identified by its
unique Spotify ID.

```java
CompletableFuture<ApiResponse<TrackObject>> getTrackAsync(
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

## Response Type

**200**: A track

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`TrackObject`](../../doc/models/track-object.md).

## Example Usage

```java
String id = "11dFghVXANMlKmJXsNCbNl";
String market = "ES";

tracksApi.getTrackAsync(id, market).thenAccept(result -> {
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


# Get-Several-Tracks

Get Spotify catalog information for multiple tracks based on their Spotify IDs.

```java
CompletableFuture<ApiResponse<ManyTracks>> getSeveralTracksAsync(
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

## Response Type

**200**: A set of tracks

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`ManyTracks`](../../doc/models/many-tracks.md).

## Example Usage

```java
String ids = "7ouMYWpwJ422jRcDASZB7P,4VqPOruhp5EdPBeR92t6lQ,2takcwOaAZWiXQijPHIx7B";
String market = "ES";

tracksApi.getSeveralTracksAsync(ids, market).thenAccept(result -> {
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


# Get-Users-Saved-Tracks

Get a list of the songs saved in the current Spotify user's 'Your Music' library.

```java
CompletableFuture<ApiResponse<PagingSavedTrackObject>> getUsersSavedTracksAsync(
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

`user-library-read`

## Response Type

**200**: Pages of tracks

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`PagingSavedTrackObject`](../../doc/models/paging-saved-track-object.md).

## Example Usage

```java
String market = "ES";
Integer limit = 10;
Integer offset = 5;

tracksApi.getUsersSavedTracksAsync(market, limit, offset).thenAccept(result -> {
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


# Save-Tracks-User

Save one or more tracks to the current user's 'Your Music' library.

```java
CompletableFuture<ApiResponse<Void>> saveTracksUserAsync(
    final String ids,
    final SaveTracksRequest body)
```

## Authentication

This endpoint requires [oauth_2_0](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `ids` | `String` | Query, Required | - |
| `body` | [`SaveTracksRequest`](../../doc/models/save-tracks-request.md) | Body, Optional | - |

## Requires scope

### oauth_2_0

`user-library-modify`

## Response Type

**200**: Track saved

`void`

## Example Usage

```java
String ids = "7ouMYWpwJ422jRcDASZB7P,4VqPOruhp5EdPBeR92t6lQ,2takcwOaAZWiXQijPHIx7B";
tracksApi.saveTracksUserAsync(ids, null).thenAccept(result -> {
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


# Remove-Tracks-User

Remove one or more tracks from the current user's 'Your Music' library.

```java
CompletableFuture<ApiResponse<Void>> removeTracksUserAsync(
    final String ids,
    final RemoveTracksRequest body)
```

## Authentication

This endpoint requires [oauth_2_0](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `ids` | `String` | Query, Required | - |
| `body` | [`RemoveTracksRequest`](../../doc/models/remove-tracks-request.md) | Body, Optional | - |

## Requires scope

### oauth_2_0

`user-library-modify`

## Response Type

**200**: Track removed

`void`

## Example Usage

```java
String ids = "7ouMYWpwJ422jRcDASZB7P,4VqPOruhp5EdPBeR92t6lQ,2takcwOaAZWiXQijPHIx7B";
tracksApi.removeTracksUserAsync(ids, null).thenAccept(result -> {
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


# Check-Users-Saved-Tracks

Check if one or more tracks is already saved in the current Spotify user's 'Your Music' library.

```java
CompletableFuture<ApiResponse<List<Boolean>>> checkUsersSavedTracksAsync(
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
String ids = "7ouMYWpwJ422jRcDASZB7P,4VqPOruhp5EdPBeR92t6lQ,2takcwOaAZWiXQijPHIx7B";

tracksApi.checkUsersSavedTracksAsync(ids).thenAccept(result -> {
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


# Get-Several-Audio-Features

Get audio features for multiple tracks based on their Spotify IDs.

```java
CompletableFuture<ApiResponse<ManyAudioFeatures>> getSeveralAudioFeaturesAsync(
    final String ids)
```

## Authentication

This endpoint requires [oauth_2_0](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `ids` | `String` | Query, Required | - |

## Response Type

**200**: A set of audio features

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`ManyAudioFeatures`](../../doc/models/many-audio-features.md).

## Example Usage

```java
String ids = "7ouMYWpwJ422jRcDASZB7P,4VqPOruhp5EdPBeR92t6lQ,2takcwOaAZWiXQijPHIx7B";

tracksApi.getSeveralAudioFeaturesAsync(ids).thenAccept(result -> {
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


# Get-Audio-Features

Get audio feature information for a single track identified by its unique
Spotify ID.

```java
CompletableFuture<ApiResponse<AudioFeaturesObject>> getAudioFeaturesAsync(
    final String id)
```

## Authentication

This endpoint requires [oauth_2_0](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `String` | Template, Required | - |

## Response Type

**200**: Audio features for one track

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`AudioFeaturesObject`](../../doc/models/audio-features-object.md).

## Example Usage

```java
String id = "11dFghVXANMlKmJXsNCbNl";

tracksApi.getAudioFeaturesAsync(id).thenAccept(result -> {
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


# Get-Audio-Analysis

Get a low-level audio analysis for a track in the Spotify catalog. The audio analysis describes the track’s structure and musical content, including rhythm, pitch, and timbre.

```java
CompletableFuture<ApiResponse<AudioAnalysisObject>> getAudioAnalysisAsync(
    final String id)
```

## Authentication

This endpoint requires [oauth_2_0](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `String` | Template, Required | - |

## Response Type

**200**: Audio analysis for one track

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`AudioAnalysisObject`](../../doc/models/audio-analysis-object.md).

## Example Usage

```java
String id = "11dFghVXANMlKmJXsNCbNl";

tracksApi.getAudioAnalysisAsync(id).thenAccept(result -> {
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


# Get-Recommendations

Recommendations are generated based on the available information for a given seed entity and matched against similar artists and tracks. If there is sufficient information about the provided seeds, a list of tracks will be returned together with pool size details.

For artists and tracks that are very new or obscure there might not be enough data to generate a list of tracks.

```java
CompletableFuture<ApiResponse<RecommendationsObject>> getRecommendationsAsync(
    final Integer limit,
    final String market,
    final String seedArtists,
    final String seedGenres,
    final String seedTracks,
    final Double minAcousticness,
    final Double maxAcousticness,
    final Double targetAcousticness,
    final Double minDanceability,
    final Double maxDanceability,
    final Double targetDanceability,
    final Integer minDurationMs,
    final Integer maxDurationMs,
    final Integer targetDurationMs,
    final Double minEnergy,
    final Double maxEnergy,
    final Double targetEnergy,
    final Double minInstrumentalness,
    final Double maxInstrumentalness,
    final Double targetInstrumentalness,
    final Integer minKey,
    final Integer maxKey,
    final Integer targetKey,
    final Double minLiveness,
    final Double maxLiveness,
    final Double targetLiveness,
    final Double minLoudness,
    final Double maxLoudness,
    final Double targetLoudness,
    final Integer minMode,
    final Integer maxMode,
    final Integer targetMode,
    final Integer minPopularity,
    final Integer maxPopularity,
    final Integer targetPopularity,
    final Double minSpeechiness,
    final Double maxSpeechiness,
    final Double targetSpeechiness,
    final Double minTempo,
    final Double maxTempo,
    final Double targetTempo,
    final Integer minTimeSignature,
    final Integer maxTimeSignature,
    final Integer targetTimeSignature,
    final Double minValence,
    final Double maxValence,
    final Double targetValence)
```

## Authentication

This endpoint requires [oauth_2_0](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `limit` | `Integer` | Query, Optional | **Default**: `20`<br><br>**Constraints**: `>= 1`, `<= 100` |
| `market` | `String` | Query, Optional | - |
| `seedArtists` | `String` | Query, Optional | - |
| `seedGenres` | `String` | Query, Optional | - |
| `seedTracks` | `String` | Query, Optional | - |
| `minAcousticness` | `Double` | Query, Optional | **Constraints**: `>= 0`, `<= 1` |
| `maxAcousticness` | `Double` | Query, Optional | **Constraints**: `>= 0`, `<= 1` |
| `targetAcousticness` | `Double` | Query, Optional | **Constraints**: `>= 0`, `<= 1` |
| `minDanceability` | `Double` | Query, Optional | **Constraints**: `>= 0`, `<= 1` |
| `maxDanceability` | `Double` | Query, Optional | **Constraints**: `>= 0`, `<= 1` |
| `targetDanceability` | `Double` | Query, Optional | **Constraints**: `>= 0`, `<= 1` |
| `minDurationMs` | `Integer` | Query, Optional | - |
| `maxDurationMs` | `Integer` | Query, Optional | - |
| `targetDurationMs` | `Integer` | Query, Optional | - |
| `minEnergy` | `Double` | Query, Optional | **Constraints**: `>= 0`, `<= 1` |
| `maxEnergy` | `Double` | Query, Optional | **Constraints**: `>= 0`, `<= 1` |
| `targetEnergy` | `Double` | Query, Optional | **Constraints**: `>= 0`, `<= 1` |
| `minInstrumentalness` | `Double` | Query, Optional | **Constraints**: `>= 0`, `<= 1` |
| `maxInstrumentalness` | `Double` | Query, Optional | **Constraints**: `>= 0`, `<= 1` |
| `targetInstrumentalness` | `Double` | Query, Optional | **Constraints**: `>= 0`, `<= 1` |
| `minKey` | `Integer` | Query, Optional | **Constraints**: `>= 0`, `<= 11` |
| `maxKey` | `Integer` | Query, Optional | **Constraints**: `>= 0`, `<= 11` |
| `targetKey` | `Integer` | Query, Optional | **Constraints**: `>= 0`, `<= 11` |
| `minLiveness` | `Double` | Query, Optional | **Constraints**: `>= 0`, `<= 1` |
| `maxLiveness` | `Double` | Query, Optional | **Constraints**: `>= 0`, `<= 1` |
| `targetLiveness` | `Double` | Query, Optional | **Constraints**: `>= 0`, `<= 1` |
| `minLoudness` | `Double` | Query, Optional | - |
| `maxLoudness` | `Double` | Query, Optional | - |
| `targetLoudness` | `Double` | Query, Optional | - |
| `minMode` | `Integer` | Query, Optional | **Constraints**: `>= 0`, `<= 1` |
| `maxMode` | `Integer` | Query, Optional | **Constraints**: `>= 0`, `<= 1` |
| `targetMode` | `Integer` | Query, Optional | **Constraints**: `>= 0`, `<= 1` |
| `minPopularity` | `Integer` | Query, Optional | **Constraints**: `>= 0`, `<= 100` |
| `maxPopularity` | `Integer` | Query, Optional | **Constraints**: `>= 0`, `<= 100` |
| `targetPopularity` | `Integer` | Query, Optional | **Constraints**: `>= 0`, `<= 100` |
| `minSpeechiness` | `Double` | Query, Optional | **Constraints**: `>= 0`, `<= 1` |
| `maxSpeechiness` | `Double` | Query, Optional | **Constraints**: `>= 0`, `<= 1` |
| `targetSpeechiness` | `Double` | Query, Optional | **Constraints**: `>= 0`, `<= 1` |
| `minTempo` | `Double` | Query, Optional | - |
| `maxTempo` | `Double` | Query, Optional | - |
| `targetTempo` | `Double` | Query, Optional | - |
| `minTimeSignature` | `Integer` | Query, Optional | **Constraints**: `<= 11` |
| `maxTimeSignature` | `Integer` | Query, Optional | - |
| `targetTimeSignature` | `Integer` | Query, Optional | - |
| `minValence` | `Double` | Query, Optional | **Constraints**: `>= 0`, `<= 1` |
| `maxValence` | `Double` | Query, Optional | **Constraints**: `>= 0`, `<= 1` |
| `targetValence` | `Double` | Query, Optional | **Constraints**: `>= 0`, `<= 1` |

## Response Type

**200**: A set of recommendations

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`RecommendationsObject`](../../doc/models/recommendations-object.md).

## Example Usage

```java
Integer limit = 10;
String market = "ES";
String seedArtists = "4NHQUGzhtTLFvgF5SZesLK";
String seedGenres = "classical,country";
String seedTracks = "0c6xIDDpzE81m2q797ordA";

tracksApi.getRecommendationsAsync(limit, market, seedArtists, seedGenres, seedTracks, null, null, null, null, null, null, null, null, null, null, null, null, null, null, null, null, null, null, null, null, null, null, null, null, null, null, null, null, null, null, null, null, null, null, null, null, null, null, null, null, null, null).thenAccept(result -> {
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

