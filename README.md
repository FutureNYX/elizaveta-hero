# elizaveta-hero

Hosting for the hero film on Elizaveta's interior-design site (Tilda).

GitHub Pages answers HTTP range requests, so these files stream: playback
starts on the first chunk instead of after a full download, and seeking
works. No account, no card, no expiry.

## Files

| File | Size | What it is |
|---|---|---|
| `media/hero.mp4` | 29.4 MB | The raw camera file. Video stream copied bit-for-bit from the original, audio removed, `faststart` set. This is the quality ceiling of the source. |
| `media/hero-lite.mp4` | 4.9 MB | 1280x960 re-encode, for save-data and 2G visitors only. |
| `media/hero-poster.webp` | 50 KB | First frame. Holds the space while the film loads. |

Both films are silent: the audio track is gone from the file, not just muted
in the player.

## The Tilda block

`tilda/hero-block.html` goes into one T123 "HTML-код" block. It picks the
file, autoplays muted when the section scrolls into view, and pauses when it
scrolls away.

## Replacing the film

Give the new file a NEW name (`hero-2.mp4`) and repoint the block at it.
Overwriting in place leaves stale copies in browser and CDN caches.
