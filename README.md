# AI Data Remover

A lightweight, privacy-first web utility to strip EXIF, C2PA, and other embedded metadata from images entirely on the client side. No server uploads, no data storage, and zero external tracking.

---

## Features

- **100% Client-Side Processing:** All stripping and re-encoding happen inside your browser using the HTML5 Canvas API. Files never leave your local machine.
- **Metadata Scrubbing:** Clears standard EXIF, IPTC, XMP, and Content Credentials (C2PA) by rasterizing pixel data into a fresh container.
- **Batch Processing:** Drop multiple images at once. Download them individually or packaged together as a single ZIP archive.
- **Automated Timestamp Naming:** Cleaned images are exported as PNG files named by generation timestamp (`YYYYMMDD_HHMMSS`).
- **Zero Build Dependencies:** Built as a standalone HTML/CSS/JS file. Runs directly in any modern browser without node modules or build pipelines.

---

## How It Works

When an image is loaded into the browser, it is drawn directly to an in-memory `<canvas>` element and exported as a new `image/png` blob via `canvas.toBlob()`.

Because the canvas re-encodes pure pixel data, any binary metadata chunks located in headers (such as EXIF APP1 blocks or C2PA JUMBF manifests) are discarded during export.

---

## Getting Started

### Run Locally

1. Clone or download this repository:
   ```bash
   git clone [https://github.com/alriazuddin/ai-data-remover.git](https://github.com/alriazuddin/ai-data-remover.git)
   cd ai-data-remover
