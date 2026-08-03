
# Currently Playing Object Item

## Class Name

`CurrentlyPlayingObjectItem`

## Cases

| Type | Factory Method |
|  --- | --- |
| [`TrackObject`](../../../doc/models/track-object.md) | CurrentlyPlayingObjectItem.fromTrackObject(TrackObject trackObject) |
| [`EpisodeObject`](../../../doc/models/episode-object.md) | CurrentlyPlayingObjectItem.fromEpisodeObject(EpisodeObject episodeObject) |

## TrackObject

### Initialization Code

#### Example

```java
CurrentlyPlayingObjectItem.fromTrackObject(
        new TrackObject.Builder()
            .build()
    )
```

## EpisodeObject

### Initialization Code

#### Example

```java
CurrentlyPlayingObjectItem.fromEpisodeObject(
        new EpisodeObject.Builder(
            "https://p.scdn.co/mp3-preview/2f37da1d4221f40b9d1a98cd191f4d6f1646ad17",
            "A Spotify podcast sharing fresh insights on important topics of the moment—in a way only Spotify can. You’ll hear from experts in the music, podcast and tech industries as we discover and uncover stories about our work and the world around us.\n",
            "<p>A Spotify podcast sharing fresh insights on important topics of the moment—in a way only Spotify can. You’ll hear from experts in the music, podcast and tech industries as we discover and uncover stories about our work and the world around us.</p>\n",
            1686230,
            false,
            new ExternalUrlObject.Builder()
                .build(),
            "https://api.spotify.com/v1/episodes/5Xt5DXGzch68nYYamXrNxZ",
            "5Xt5DXGzch68nYYamXrNxZ",
            Arrays.asList(
                new ImageObject.Builder(
                    "https://i.scdn.co/image/ab67616d00001e02ff9ca10b55ce82ae553c8228\n",
                    300,
                    300
                )
                .build()
            ),
            false,
            false,
            Arrays.asList(
                "fr",
                "en"
            ),
            "Starting Your Own Podcast: Tips, Tricks, and Advice From Anchor Creators\n",
            "1981-12-15",
            ReleaseDatePrecision.DAY,
            Type5.EPISODE,
            "spotify:episode:0zLhl3WsOCQHbe1BPTiHgr",
            new ShowBase.Builder(
                Arrays.asList(
                    "available_markets0",
                    "available_markets1",
                    "available_markets2"
                ),
                Arrays.asList(
                    new CopyrightObject.Builder()
                        .build()
                ),
                "description4",
                "html_description4",
                false,
                new ExternalUrlObject.Builder()
                    .build(),
                "href8",
                "id6",
                Arrays.asList(
                    new ImageObject.Builder(
                        "https://i.scdn.co/image/ab67616d00001e02ff9ca10b55ce82ae553c8228\n",
                        300,
                        300
                    )
                    .build()
                ),
                false,
                Arrays.asList(
                    "languages7",
                    "languages6",
                    "languages5"
                ),
                "media_type6",
                "name6",
                "publisher6",
                Type6.SHOW,
                "uri0",
                198
            )
            .build()
        )
        .language("en")
        .build()
    )
```

