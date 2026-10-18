# LaserProfit Pro Mobile — companion MVP

A mobile-first, installable Progressive Web App (PWA) for iPhone and Android.

## Included
- Dark navy / gold mobile interface
- Pricing calculator (material, waste, labor, machine, overhead, target gross margin)
- Add, edit, and delete customers, materials, and quotes
- Private internal notes on customers, materials, and quotes
- Multiple-quote selection and browser Print / Save as PDF, without internal notes
- Business name/contact information and optional small logo for printed PDFs
- Offline app shell via service worker after first successful load
- JSON export/import backup **for this mobile app only**

## Important limitations
- **No automatic Windows desktop synchronization**. The Windows app uses SQLite; this mobile MVP uses browser localStorage. Its JSON backups are NOT interchangeable with the Windows SQLite database.
- Mobile data is specific to the browser/device. Export backups regularly; clearing site data may erase records.
- This is a development MVP, not a production-tested commercial release. Test on actual iPhone and Android devices before selling.
- Printing to PDF uses the browser/system print dialog, not a bundled PDF library.
- A PWA needs HTTPS hosting to be installed and used offline reliably. Opening `index.html` directly as a local file is only useful for limited previewing.
- For proper cross-device sync, build an authenticated API and a desktop synchronization module, with conflict handling and backup/restore.

## Run locally for testing
From the extracted folder:

    py -m http.server 8080

Visit `http://localhost:8080` on your computer. For phone installation, deploy these static files to a secure HTTPS host (such as GitHub Pages or Cloudflare Pages), then open the URL on the phone and use Add to Home Screen / Install App. Hosting is separate from this package.

## One-time purchase model
A standalone PWA URL cannot reliably enforce paid licenses by itself. Before selling, add secure license validation and an entitlement service or distribute through an appropriate app store. Never place secret license keys in frontend JavaScript.
