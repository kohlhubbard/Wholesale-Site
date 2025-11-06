# Wholesale-Site

## Social preview asset

This project references `https://hhrealtyteam.com/og-image.jpg` for Open Graph and Twitter previews. Deployments should publish a 1200×630 JPEG at that path. To recreate the image without committing a binary asset, use your preferred design tool (Figma, Canva, etc.) or run a one-off render step during deployment that uploads the file to object storage/CDN alongside the site output.

Example ImageMagick command:

```bash
magick -size 1200x630 canvas:'#0b3b60' \
  -gravity center -font 'Helvetica-Bold' -fill '#ffffff' \
  -pointsize 80 -annotate +0-40 'HH Realty Team' \
  -pointsize 48 -annotate +0+80 'We buy houses fast for cash' \
  og-image.jpg
```

Upload the generated `og-image.jpg` to your hosting provider so it is served from the site root with `Content-Type: image/jpeg`, `Cache-Control: max-age=3600, public`, and HTTP 200 status.
