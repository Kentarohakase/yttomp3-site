# yttomp3.kentser.com

Landing page for [AudioQualityEnhancer](https://github.com/Kentarohakase/AudioQualityEnhancer) —
a Windows desktop app that downloads the best audio stream of a URL and enhances it (EBU R128
loudness normalization, lossless FLAC, metadata and cover art) instead of re-encoding a lossy
stream like typical yt-to-mp3 sites.

Static single page (`index.html`), no build step, no dependencies. Served via GitHub Pages from
the `main` branch root; the custom domain is set through the `CNAME` file.

## Deploy / DNS

1. GitHub Pages is enabled for this repo (branch `main`, path `/`).
2. Add a DNS record at the `kentser.com` zone: `CNAME yttomp3 -> kentarohakase.github.io.`
3. The `CNAME` file in this repo points Pages at `yttomp3.kentser.com`.
