MSF OCA LAB COMPETENCY TRACKER — PHONE APP (PWA)
=================================================

WHAT THIS FOLDER IS
-------------------
A complete, installable phone app. It is made of plain web files:
  index.html ............ the tracker app (all features)
  manifest.webmanifest .. tells the phone it is an installable app
  sw.js ................. makes it work offline once installed
  icon-*.png ............ app icons for the home screen

There is NO server, NO database, NO backend to run or maintain.

IMPORTANT — WHERE THE DATA LIVES (for IT / data protection)
-----------------------------------------------------------
The host only delivers these CODE files to the phone, exactly like
serving a normal web page. ALL data entered in the app (staff names,
checklists, assessment results) is stored ONLY in the phone's own
local browser storage (IndexedDB). No staff or patient data is ever
sent to the host or anywhere else. Hosting the app is not hosting data.

HOW TO PUBLISH IT (pick ONE — takes ~2 minutes)
-----------------------------------------------
OPTION A — Netlify Drop (easiest, no account technical setup):
  1. Go to  https://app.netlify.com/drop
  2. Drag this WHOLE folder onto the page.
  3. It returns a permanent https link, e.g. lab-tracker.netlify.app
  Done. Share that link with assessors.

OPTION B — GitHub Pages:
  1. Create a repository and upload all files in this folder to it.
  2. Settings > Pages > Source: deploy from branch (main, root "/").
  3. It returns an https link, e.g. your-name.github.io/lab-tracker
  Done.

OPTION C — Inside MSF (private): ask IT to publish these files on
  Azure Static Web Apps (free) or any internal HTTPS static address.
  NOTE: a SharePoint document library will NOT work — it downloads the
  file instead of running it.

HOW ASSESSORS INSTALL IT (on the phone)
---------------------------------------
  1. Open the link in Chrome (Android) while online, just once.
  2. Tap the "Install app" button (bottom-right) — or Chrome menu >
     "Add to Home screen" / "Install app".
  3. It now has a home-screen icon and opens full-screen like an app.
  4. After this first install it works fully OFFLINE — no signal needed.

UPDATING THE APP LATER
----------------------
  1. Replace index.html with the new version.
  2. Open sw.js and change the version, e.g.  v1  ->  v2  (one line).
  3. Re-publish the folder the same way.
  Installed phones pick up the update next time they are online.

DATA BACKUP (recommended)
-------------------------
Because data lives on each device, use the app's built-in export/backup
periodically so assessments are not lost if a phone is wiped or replaced.
