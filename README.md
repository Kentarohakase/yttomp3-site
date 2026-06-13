# yttomp3.kentser.com

Landing page for [AudioQualityEnhancer](https://github.com/Kentarohakase/AudioQualityEnhancer) —
a Windows desktop app that downloads the best audio stream of a URL and enhances it (EBU R128
loudness normalization, lossless FLAC, metadata and cover art) instead of re-encoding a lossy
stream like typical yt-to-mp3 sites.

Static single page (`index.html`), no build step, no dependencies.

## Deployment

On every push to `main`, a GitHub Actions workflow uploads the site to the easyname webspace
via FTPS (`.github/workflows/deploy.yml`).

### Required GitHub secrets (Settings → Secrets and variables → Actions)

- `FTP_SERVER` — easyname FTP host (e.g. `ftp.kentser.com` or the host from the easyname panel)
- `FTP_USERNAME` — FTP account user
- `FTP_PASSWORD` — FTP account password

### Optional repository variable

- `FTP_SERVER_DIR` — target folder on the webspace for `yttomp3.kentser.com`
  (defaults to `./`; set it to the subdomain's document root, e.g. `/yttomp3.kentser.com/`).

### DNS

The `yttomp3` subdomain is managed at easyname and must point at the easyname webspace
(create the subdomain in the easyname panel and map it to the folder this workflow deploys to).
