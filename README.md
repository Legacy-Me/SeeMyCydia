# SeeMyCydia

Access the live generator here: https://legacy-me.github.io/seemycydia/

SeeMyCydia is a powerful, client-side HTML/JS generator designed to compile and export fully functional, static APT repositories for jailbroken iOS devices. It allows you to build custom repositories compatible with **Cydia, Sileo, Zebra, and Installer** entirely within your web browser—no server-side backend required.

Created by **RetroWeirdos**.

---

## Features

* **100% Client-Side Compilation:** Generates a complete repository structure (`debs/`, `icons/`, `index.html`) using JSZip directly in the browser.
* **Automated Cryptographic Hashing:** Uses `CryptoJS` to automatically calculate and inject precise **MD5, SHA-1, and SHA-256** checksums for all uploaded `.deb` packages and the root `Release` manifest.
* **Multi-Format Architecture Support:** Uses `pako` and `bzip2.js` to automatically encode `Packages.gz` and `Packages.bz2` database variants alongside standard text, ensuring legacy and modern package manager compatibility.
* **Classic iOS 6 UI:** Features an authentic, glossy iOS 6 inspired interface and custom-built modal notification physics.
* **Smart Security Bypass:** Specifically structured to prevent Windows SmartScreen and Defender from flagging extensionless index manifests as false positives.

---

## How to Use the Generator

1. **Launch the Dashboard:** Open https://legacy-me.github.io/seemycydia/ in any modern web browser.
2. **Configure Repo Settings:** 
   * Set your **Repository Name** and **Root URL** (e.g., your GitHub Pages domain).
   * Upload a **120x120px Repo Icon**.
   * Add an "About Me" bio.
3. **Map Your Tweaks:**
   * Upload your tweak's `.deb` file and an optional `.png` icon.
   * Fill out the metadata: Package Name, Bundle ID (e.g., `com.retroweirdos.tweak`), Version, Section, and Dependencies.
   * Add a short subtitle and list out the tweak's features.
   * Click **Build & Save Tweak** (or **Add More Packages** to queue multiple tweaks at once).
4. **Compile & Export:** Click the green **Compile & Export Suite ZIP** button. The dashboard will process your files, calculate all hashes, compress the manifests, and download a `.zip` file to your computer.

---

## CRITICAL: Extraction & Deployment

**DO NOT use the default Windows File Explorer to extract the downloaded ZIP.**
Because standard APT repositories use extensionless files (like `Release` and `Packages`), the default Windows extractor may corrupt them or trigger false-positive security warnings.

1. **Extract with 7-Zip:** You **must** use [7-Zip](https://www.7-zip.org/) to extract the generated ZIP file safely.
2. **Review Icon Assets:** Ensure your branding assets are named and placed correctly in the root folder before deploying:
   * `icons/LOGO.png` — The main brand logo shown on the web page header.
   * `icons/GLOBEICON.png` — The high-density favicon shown on the browser tab.
3. **Deploy:** Upload the entire extracted folder structure directly to the root of your hosting provider (like GitHub Pages).

Your repository is now live! Users can visit your URL to view your custom dashboard or tap the native "Add to Cydia/Sileo/Zebra" buttons to add the source directly to their device.

---

### Built With
* [JSZip](https://stuk.github.io/jszip/)
* [Pako (Zlib/Gzip)](https://github.com/nodeca/pako)
* [CryptoJS](https://cryptojs.gitbook.io/docs/)
* [bzip2.js](https://github.com/antimatter15/bzip2.js)
