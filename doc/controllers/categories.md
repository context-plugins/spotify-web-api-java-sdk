# Categories

```java
CategoriesApi categoriesApi = client.getCategoriesApi();
```

## Class Name

`CategoriesApi`

## Methods

* [Get-Categories](../../doc/controllers/categories.md#get-categories)
* [Get-a-Category](../../doc/controllers/categories.md#get-a-category)


# Get-Categories

Get a list of categories used to tag items in Spotify (on, for example, the Spotify player’s “Browse” tab).

```java
CompletableFuture<ApiResponse<PagedCategories>> getCategoriesAsync(
    final String locale,
    final Integer limit,
    final Integer offset)
```

## Authentication

This endpoint requires [oauth_2_0](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `locale` | `String` | Query, Optional | - |
| `limit` | `Integer` | Query, Optional | **Default**: `20`<br><br>**Constraints**: `>= 1`, `<= 50` |
| `offset` | `Integer` | Query, Optional | **Default**: `0` |

## Response Type

**200**: A paged set of categories

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`PagedCategories`](../../doc/models/paged-categories.md).

## Example Usage

```java
String locale = "sv_SE";
Integer limit = 10;
Integer offset = 5;

categoriesApi.getCategoriesAsync(locale, limit, offset).thenAccept(result -> {
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


# Get-a-Category

Get a single category used to tag items in Spotify (on, for example, the Spotify player’s “Browse” tab).

```java
CompletableFuture<ApiResponse<CategoryObject>> getACategoryAsync(
    final String categoryId,
    final String locale)
```

## Authentication

This endpoint requires [oauth_2_0](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `categoryId` | `String` | Template, Required | - |
| `locale` | `String` | Query, Optional | - |

## Response Type

**200**: A category

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`CategoryObject`](../../doc/models/category-object.md).

## Example Usage

```java
String categoryId = "dinner";
String locale = "sv_SE";

categoriesApi.getACategoryAsync(categoryId, locale).thenAccept(result -> {
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

