# MintRx Email Assets

CDN host for MintRx marketing email images. Served via `raw.githubusercontent.com`.

## URL pattern

```
https://raw.githubusercontent.com/JAlmanzarMint/mintrx-email-assets/main/<send-folder>/<image.jpg>
```

## Folder convention

```
YYYY-MM-DD-<slug>/
  hero.jpg
  card-<product>.jpg
  ...
shared/
  logo.png
  ig-icon.png
```

One folder per send. Date-prefix so sends sort chronologically. Slug matches the per-send working directory under `~/MintRx-Marketing/sends/`.

## Adding a new send

```bash
cd ~/mintrx-email-assets
mkdir 2026-MM-DD-<slug>
cp <local-images>/* 2026-MM-DD-<slug>/
git add . && git commit -m "Add YYYY-MM-DD-<slug> assets" && git push
```

Image is live at the raw URL ~10-30 seconds after push.

## Image rules

- JPG quality 85 progressive, hero ~150KB, cards ~50KB
- Reference in email HTML via the raw.githubusercontent.com URL (NOT relative paths)
- For Gmail [TEST] sends via the inline-CID sender, use relative paths during dev — swap to raw URLs only in the Attentive production HTML
