# yttomp3.kentser.com

Landing page for [AudioQualityEnhancer](https://github.com/Kentarohakase/AudioQualityEnhancer) —
a Windows desktop app that downloads the best audio stream of a URL and enhances it (EBU R128
loudness normalization, lossless FLAC, metadata and cover art) instead of re-encoding a lossy
stream like typical yt-to-mp3 sites.

Static single page (`index.html`), no build step, no dependencies.

## Deployment

On every push to `main`, a GitHub Actions workflow uploads the site to the easyname webspace
via SFTP (port 22) (`.github/workflows/deploy.yml`).

### Required GitHub secrets (Settings → Secrets and variables → Actions)

- `FTP_SERVER` — easyname SFTP host from the easyname panel (the SSH/SFTP server)
- `FTP_USERNAME` — SFTP account user
- `FTP_PASSWORD` — SFTP account password

### Optional repository variable

- `FTP_SERVER_DIR` — target folder on the webspace for `yttomp3.kentser.com`
  (defaults to `./`; set it to the subdomain's document root, e.g. `/yttomp3.kentser.com/`).

### DNS

The `yttomp3` subdomain is managed at easyname and must point at the easyname webspace
(create the subdomain in the easyname panel and map it to the folder this workflow deploys to).
