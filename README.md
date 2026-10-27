# Birthday → Birthday Surprise → Appreciation

This repository packages three connected stages:

1. `site-root/` — the new birthday landing page. Its final button leads to `birthday/index.html`.
2. `birthday/` — the second birthday experience. Its Continue button stays locked until **28 October 2026, 08:30 IST (TEST RELEASE)**.
3. `private/appreciation-site.tar.gz.enc` — the appreciation site, encrypted and excluded from deployment before the deadline. After release, it is published at `/appreciation/`.

## GitHub Pages setup

- Set Pages source to **GitHub Actions**.
- Keep workflow permissions sufficient to deploy Pages.
- Add/update the repository Actions secret named `SORRY_DECRYPTION_KEY` with the value from the separately supplied key file. Do not commit or upload the key file.
- Push the files to `main`. Before the deadline, deployments include only the first two stages. The scheduled workflow runs at 03:00 UTC on 28 October 2026 (08:30 IST on 28 October; TEST RELEASE); scheduled GitHub Actions may start a little late, so the lock itself also checks the exact deadline.

The appreciation archive uses OpenSSL AES-256-CBC with PBKDF2 (200,000 iterations). Keep the secret key private.
