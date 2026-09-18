# elizaveta-hero

Hosting for the hero film on Elizaveta Manina's site, maninaelizaveta.tilda.ws.

GitHub Pages answers HTTP range requests, so these files stream: playback
starts on the first chunk instead of after a full download, and seeking
works. No account, no card, no expiry.

## Why not just upload to Tilda

Tilda re-encodes video on upload. The copy currently on the live page came
back at **1.5 Mbps**, and it had been padded from 4:3 out to 16:9, so a share
of even that small bitrate is spent on black bars rather than on the picture.
That is the whole reason the film looks soft there.

`hero-sound.mp4` here is **9.1 Mbps with no bars**, because nothing re-encoded it.

## Files

| File | Size | What it is |
|---|---|---|
| `media/hero-sound.mp4` | 29.8 MB | The raw camera file. Picture and sound both copied bit-for-bit from the original, `faststart` set. The quality ceiling of the source. |
| `media/hero-sound-lite.mp4` | 5.2 MB | 1280x960 re-encode, for save-data and 2G visitors only. |
| `media/hero-poster.webp` | 50 KB | First frame. Holds the space while the film loads. |

## The Tilda block

`tilda/hero-block.html` goes into one T123 "HTML-код" block. It carries the
cover's existing text, autoplays muted when the section scrolls into view,
pauses when it scrolls away, and has a sound button at the bottom right.

## Replacing the film

Give the new file a NEW name (`hero-2.mp4`) and repoint the block at it.
Overwriting in place leaves stale copies in browser and CDN caches.
