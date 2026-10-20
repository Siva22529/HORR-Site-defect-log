# Site Defect Log

Phone app for daily site inspections on highway projects. Take a photo of a defect, get the chainage automatically from the road alignment (KMZ), choose the category and defect type, and produce the Aarvee-format Word report.

## Install on Android

1. Open **Releases** on this repository page (right side) on your phone.
2. Tap **SiteDefectLog.apk** under the latest release to download it.
3. Open the downloaded file. If Android asks, allow installs from this source (Chrome or Files).
4. Open **Site Defect Log** and allow Camera and Location when asked.

Each push to `main` builds a new APK automatically (Actions tab). New versions install over the old one and keep your data.

## Report format

Company name, project, inspector name and inspection date at the top, then a table:
S. No. | Chainage | Category (MCW-LHS / MCW-RHS / Left Service Road / Right Service Road) | Type of Defect | Image

## Alignment

The app ships with the Hyderabad ORR centre line (CL folder of `ORR_UTM_KML_12.09.2023.kmz`, 153.76 km closed loop). Load any other KMZ in Setup. Use **Calibrate at a km stone** once so GPS chainage matches the stones.

## Data

Defects and photos are stored on the phone. Use **Setup → Back up** regularly; the backup JSON includes photos and can be restored on another phone.

## Project layout

- `www/index.html` – the whole app (HTML, CSS, JS)
- `www/lib/` – JSZip (KMZ reading) and docx (Word report), bundled for offline use
- `android/` – Capacitor Android project (camera and location permissions, fixed signing key so updates install over each other)
- `.github/workflows/build-apk.yml` – builds the APK on GitHub
