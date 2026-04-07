# Booth 40 BLO Helper App

A highly-optimized, offline-first Progressive Web Application (PWA) designed to assist the Booth Level Officer (BLO) for Booth 40 (Thiruvalla 111) during the Legislative Assembly Kerala Election 2026.

## Features
- **Offline Capable:** Full Progressive Web App (PWA) that installs on your device and works completely offline with Service Workers.
- **Lightning Fast Search:** Features bigram-based fuzzy finding to locate probable matches for misspelled names or missing records across 900+ voters.
- **Dynamic Filtering:** Search by serial number, House name, Voter name, relative name, or dynamically sub-filter based on existing record distributions.
- **Smart Natural Language Assistant:** Contains an on-device NLP chatbot that allows natural language voice queries using Web Speech API (e.g., "Find John", "How many male voters").
- **Field Reporting:** One-tap ability to mark electors as Death, Shifted, Removed, or Active.
- **Localization:** Open map integration, GPS geocoding, and one-click WhatsApp messaging pre-populated with localized Malayalam and English voter card details.
- **Data Extensibility:** Export field updates (custom phone numbers, geolocation strings, status states) via JSON backups, and export compiled lists to an Excel-friendly CSV.

## Getting Started

### Hosting via GitHub Pages
To easily distribute this PWA to your field agents:
1. Create a fresh GitHub repository.
2. Push all contents (including `index.html`, `manifest.json`, `sw.js`, `voters_data.js`, and icon files) to the `main` branch.
3. Turn on GitHub Pages (Settings -> Pages -> Branch: Main).
4. Have your agents navigate to your `https://yourusername.github.io/repo-name/` URL on Chrome Android, and click "Install" on the popup.

### Development & Extensibility
Modification to datasets happens predominantly within `voters_data.js` via the `rawCSVText` block. The data relies on a strict comma-separated 10-column scheme schema format mapping:
`Serial,Name,EName,Relative,HouseNo,HouseName,EHouseName,Sex,IDCard,Status`
Any deviations (such as extra commas) will offset alignments, so be sure to sanitize inputs.

## Technologies Used
- HTML / Vanilla Javascript (ES6) / CSS3
- Service Workers (PWA)
- Bigram Dice Coefficient Fuzzy Logic Algorithm
- Web Speech API and Geolocation API

## Data Backup
Custom data (additions, mobile numbers, new mappings) strictly persists via your browser's `localStorage` to bypass database dependencies in the field. To survive browser cache deletion, periodically use the **Backup Sync** feature on the menu panel to download the `.json` snapshot of the system.
