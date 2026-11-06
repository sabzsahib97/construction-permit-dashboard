# Free Multi-County Construction Permit Dashboard

A static dashboard for GitHub Pages. No paid hosting, keys, or backend required.

## Launch
1. Create a new GitHub repository, e.g. `construction-permit-dashboard`.
2. Upload `index.html`, `config.json`, and `README.md` to the repository root.
3. Go to Settings > Pages > Build and deployment > Deploy from a branch, select `main` and `/ (root)`, then Save.
4. Visit the GitHub Pages URL shown under Settings > Pages.
5. Export each county's `Construction Leads` tab as a CSV from Google Sheets (File > Download > Comma Separated Values), name each CSV with the county name, and upload it using the dashboard's file input.

## Optional live Google Sheets feeds
In Google Sheets, use File > Share > Publish to web, select the `Construction Leads` tab and CSV format, then copy its published CSV URL into the matching `url` value in `config.json`. Commit the change. Reload the dashboard to pull published data.

WARNING: Publishing a Google Sheet tab makes that data accessible to anyone with the link, including contact details. Do NOT publish private information or business contact data you do not intend to expose publicly. To keep sheets private, use manual CSV upload in your browser instead. GitHub Pages itself is a public website, and it cannot safely store service-account credentials.

## Supported columns
Brunswick and Charleston's current `Construction Leads` columns are recognized. Other county CSVs are recognized if they use standard headers such as `Permit Number`, `Address`, `Description`, `Contractor Name`, `Contractor Phone`, `Contractor Email`, `Priority`, `Trade Opportunity`.

## Current limits
- CSV uploads are browser-local and reset on reload. Published feeds auto-load on each page visit.
- Contact-ready count requires a contractor name, phone/email, and explicit role verification. A public business contact is not automatically a verified permit contractor.
- Georgetown can appear in filters while awaiting a verified public permit feed.
- Horry historical data must not be presented as fresh permits.
- This starter shows the first 300 filtered records for performance. Counts use all loaded records.
- For truly shared private live data, a future authenticated backend is required; GitHub Pages alone cannot securely access private Google Sheets.
