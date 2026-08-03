# Search

```java
SearchApi searchApi = client.getSearchApi();
```

## Class Name

`SearchApi`


# Search

Get Spotify catalog information about albums, artists, playlists, tracks, shows, episodes or audiobooks
that match a keyword string. Audiobooks are only available within the US, UK, Canada, Ireland, New Zealand and Australia markets.

```java
CompletableFuture<ApiResponse<SearchItems>> searchAsync(
    final String q,
    final List<Itemtype> type,
    final String market,
    final Integer limit,
    final Integer offset,
    final IncludeExternal includeExternal)
```

## Authentication

This endpoint requires [oauth_2_0](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `q` | `String` | Query, Required | - |
| `type` | [`List<Itemtype>`](../../doc/models/itemtype.md) | Query, Required | - |
| `market` | `String` | Query, Optional | - |
| `limit` | `Integer` | Query, Optional | **Default**: `20`<br><br>**Constraints**: `>= 1`, `<= 50` |
| `offset` | `Integer` | Query, Optional | **Default**: `0`<br><br>**Constraints**: `>= 0`, `<= 1000` |
| `includeExternal` | [`IncludeExternal`](../../doc/models/include-external.md) | Query, Optional | - |

## Response Type

**200**: Search response

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`SearchItems`](../../doc/models/search-items.md).

## Example Usage

```java
String q = "remaster%20track:Doxy%20artist:Miles%20Davis";
List<Itemtype> type = Arrays.asList(
    Itemtype.AUDIOBOOK,
    Itemtype.ALBUM,
    Itemtype.ARTIST
);

String market = "ES";
Integer limit = 10;
Integer offset = 5;

searchApi.searchAsync(q, type, market, limit, offset, null).thenAccept(result -> {
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

