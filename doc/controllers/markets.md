# Markets

```java
MarketsApi marketsApi = client.getMarketsApi();
```

## Class Name

`MarketsApi`


# Get-Available-Markets

Get the list of markets where Spotify is available.

```java
CompletableFuture<ApiResponse<Markets>> getAvailableMarketsAsync()
```

## Authentication

This endpoint requires [oauth_2_0](../../doc/auth/oauth-2-authorization-code-grant.md)

## Response Type

**200**: A markets object with an array of country codes

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`Markets`](../../doc/models/markets.md).

## Example Usage

```java
marketsApi.getAvailableMarketsAsync().thenAccept(result -> {
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

