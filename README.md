# SeeMyCydia

Access the live generator here: https://legacy-me.github.io/SeeMyCydia/

SeeMyCydia is a powerful, client-side HTML/JS generator designed to compile and export fully functional, static APT repositories for jailbroken iOS devices. It allows you to build custom repositories compatible with **Cydia, Sileo, Zebra, and Installer** entirely within your web browser—no server-side backend required.

Created by **RetroWeirdos**.

---

## Compatibility Across Operating Systems

SeeMyCydia is built entirely on client-side web technologies (HTML, CSS, and JavaScript), making it universally compatible across all major operating systems:

* **Windows:** Fully functional in all modern browsers (Chrome, Edge, Firefox). When downloading the generated repository, use **7-Zip** to extract files, as native Windows extraction may flag extensionless repository files as potentially harmful.
* **macOS:** Compatible with Safari, Chrome, and Firefox. macOS handles extensionless files (like `Packages` and `Release`) natively, making the extraction and deployment process seamless.
* **Linux:** Operates perfectly in all Linux-based browsers. You can use standard command-line tools like `unzip` to extract the repo and prepare it for deployment without any security intervention.
* **Mobile/Tablet:** The generator interface is responsive and can be used on iPadOS or Android browsers to map packages and compile your repository ZIP on the go.

---

## Features

* **100% Client-Side Compilation:** Generates a complete repository structure (`debs/`, `icons/`, `index.html`) using JSZip directly in the browser.
* **Automated Cryptographic Hashing:** Uses `CryptoJS` to automatically calculate and inject precise **MD5, SHA-1, and SHA-256** checksums for all uploaded `.deb` packages and the root `Release` manifest.
* **Multi-Format Architecture Support:** Uses `pako` and `bzip2.js` to automatically encode `Packages.gz` and `Packages.bz2` database variants alongside standard text, ensuring legacy and modern package manager compatibility.
* **Classic iOS 6 UI:** Features an authentic, glossy iOS 6 inspired interface and custom-built modal notification physics.
* **Smart Security Bypass:** Specifically structured to prevent Windows SmartScreen and Defender from flagging extensionless index manifests as false positives.

---

## How to Use the Generator

1. **Launch the Dashboard:** Open https://legacy-me.github.io/SeeMyCydia/ in any modern web browser.
2. **Configure Repo Settings:** 
   * Set your **Repository Name** and **Root URL**.
   * Upload a **120x120px Repo Icon**.
   * Add an "About Me" bio.
3. **Map Your Tweaks:**
   * Upload your tweak's `.deb` file and an optional `.png` icon.
   * Fill out the metadata: Package Name, Bundle ID, Version, Section, and Dependencies.
   * Add a short subtitle and list out the tweak's features.
   * Click **Build & Save Tweak** (or **Add More Packages** to queue multiple tweaks at once).
4. **Compile & Export:** Click the green **Compile & Export Suite ZIP** button. Follow the on-screen prompts to download your repository.

---

## CRITICAL: Extraction & Deployment

Because standard APT repositories use extensionless files (like `Release` and `Packages`), Windows users **must** use [7-Zip](https://www.7-zip.org/download.html) to extract the generated ZIP file safely.

1. **Review Icon Assets:** Ensure your branding assets are named and placed correctly in the root folder before deploying:
   * `icons/LOGO.png` — The main brand logo shown on the web page header.
   * `icons/GLOBEICON.png` — The high-density favicon shown on the browser tab.
2. **Deploy:** Upload the entire extracted folder structure directly to the root of your hosting provider (like GitHub Pages).

Your repository is now live! Users can visit your URL to view your custom dashboard or tap the native "Add to Cydia/Sileo/Zebra" buttons to add the source directly to their device.

---

### Built With
* [JSZip](https://stuk.github.io/jszip/)
* [Pako (Zlib/Gzip)](https://github.com/nodeca/pako)
* [CryptoJS](https://cryptojs.gitbook.io/docs/)
* [bzip2.js](https://github.com/antimatter15/bzip2.js)