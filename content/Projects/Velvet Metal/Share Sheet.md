---
title: Share Sheet
tags:
  - velvet-metal
  - share-sheet
  - docs
---

# Share Sheet

The share sheet functionality was the first seed of inspiration for the entire project and is the thing most people have been excited about when I give them the elevator pitch. I’m going to provide some behind the scenes insight into what’s happening when you click the *Velvet Metal* share sheet icon.

1. User clicks the share *[Album/Song/Playlist]* button in their respective app and proceeds to click the *Velvet Metal* icon.
2. Upon clicking the *Velvet Metal* icon the incoming URL is parsed. It detects if the music item is a song, playlist, or album and reaches out to the respective API with that ID to fetch the details for the item.
3. We do our matching based on ISRC because ISRCs help identify recordings across different services, borders, and licensing deals. It was decided that this can account for spelling differences and/or situations where there are “various artists” fields that may populate and skew the artist name fields of the returned data.
4. Once the ISRC is found for the given item we take that ISRC and use it to hit the source service API as a search query. It then finds the exact match in the other service, generates a url for that service, and returns it to the user.
5. The user then has the option to copy the link of the source URL item or simply open up the item in the native app of their choice.
6. Voila.

## Apple Music URLs

### Album

`https://music.apple.com/us/album/strongs-dr/1662843187 `

### Song

`https://music.apple.com/us/album/east-of-the-405/1662843187?i=1662845547 `

### Playlist

`https://music.apple.com/us/playlist/siempre-tu-pablo/pl.u-yZyV99AuY6b9Y2r `

## Spotify URLs

### Song

`https://open.spotify.com/track/7xzoolT85yNpv7xrSdn35E?si=67032f1f3f3b4304`

### Album

`https://open.spotify.com/album/3HN0QjWQJSzQPRXiJRxhzX?si=K5KYjka8TRiDbNhgjZdZvA `

### Playlist

`https://open.spotify.com/playlist/1hLtox6nmu11mIluNf8OxT?si=ardmo8oNQJ2etJyzuZiVgQ`


