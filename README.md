<div align=center> <p> <img src="favicon.svg" width="192" height="192">
<h1>LuaMani</h1>
  
***The*** *High-Performance Steam Lua & Manifest Search Engine.*

![License](https://img.shields.io/badge/license-MIT-red?style=for-the-badge)
![Status](https://img.shields.io/badge/status-OPERATIONAL-success?style=for-the-badge)
![Version](https://img.shields.io/badge/version-1.3-blue?style=for-the-badge)

</div>

---

* **LuaMani** is a web tool designed to locate, validate, and retrieve game manifest files and Lua scripts via Steam AppIDs. It features a **"Daisy-Chain" search algorithm** that scans multiple (Right now only 1) repository endpoints automatically, ensuring you find the file you need without checking dead links. The chain sequence is optimized to find and download a file in no time.
* **Why LuaMani?** Stop wasting time checking dead links. LuaMani streamlines the search for essential game files (Lua scripts, manifests, and binaries), providing instant Steam verification and intelligent failover to ensure you get the files you need from community repositories quickly.

---

## ⚡ Features

* **Dual Search Modes:** Search by **Steam AppID** or **Game Name** with live results and thumbnails
* **Smart Pre-Check:** Automatically verifies if a game exists before attempting to search repositories
* **Intel Upgrade:** Detects and displays the File Size (MB/GB) before you download
* **Daisy-Chain Logic:** Iterates through multiple repository endpoints until a valid source is found
* **Multi-Proxy Fallback:** Uses multiple CORS proxies for maximum reliability
* **Game Intelligence:** Detects Denuvo DRM, online-only games, and displays genre tags
* **Zero-bloat UI:** A premium dark-mode interface designed for modders
* **Live Updates:** Built-in version checking to ensure you're always current
* **One-Click Copy:** Click the AppID to copy instantly

---

## 🌐 Website

LuaMani is officially hosted at:
  * https://luamani.vercel.app
  * https://goat42069.github.io/LuaMani/
    
*Note: Always check the URL and reviews when using third-party instances.*

---

## 🚀 Usage Guide

LuaMani is a frontend-only tool, meaning it runs entirely in your browser.

### **Search by Game Name (NEW in v1.3)**
1. Click the **NAME_SEARCH** tab
2. Start typing a game name (e.g., "Terraria", "Garry's Mod")
3. Select from live search results with thumbnails
4. Click **INITIALIZE** to verify the target
5. Click **EXECUTE DOWNLOAD** to begin the daisy-chain search

### **Search by AppID (Traditional)**
1. Use the **ID_SELECTOR** tab (default)
2. Enter a valid Steam AppID (e.g., 4000 for Garry's Mod, 105600 for Terraria)
3. Click **INITIALIZE** to fetch game metadata
4. Click **EXECUTE DOWNLOAD** to begin the daisy-chain search

### **Advanced Features**
- **Click the AppID** in the results to copy it instantly
- **View warnings** for Denuvo-protected or online-only games
- **Check genre tags** to understand the game type
- **Monitor the log** to see which providers are being checked

### ⚠️ Error Handling
* **TARGET NOT FOUND** - Invalid AppID or game name, or network issues
* **SEARCH FAILED** - Daisy-Chain exhausted all providers without finding the file
* **PROXY OFFLINE** - All CORS proxies are unreachable (try refreshing)
* **[FAIL]`<PROVIDER>`: Status 404/403** - Failed to reach provider API or provider has no files for that `appID`
* **All providers exhausted** - No provider has files for that `appID` or no providers in the `API_LIST`

---

## 🆕 What's New in v1.3

### **Major Enhancements:**
- 🎯 **Dual Search System** - Search by AppID OR Game Name
- 🖼️ **Visual Search Results** - Game thumbnails and live filtering
- ⚠️ **Smart Warnings** - Denuvo and online-only game detection
- 🏷️ **Genre Tags** - See game categories at a glance
- 🔄 **Multi-Proxy System** - 5 different proxy fallbacks for reliability
- 📋 **One-Click Copy** - Click AppID to copy instantly
- 🔔 **Update Notifications** - Built-in version checking
- 🎨 **Premium UI** - Complete visual overhaul with hero sections

### **Technical Improvements:**
- SVG favicon for better performance and scaling
- Enhanced error handling and user feedback
- Better responsiveness and robustness
- Improved logging and status indicators

---

## 🤝 Contributing

The community is encouraged to submit valid API endpoints or UI improvements. Your contributions help keep the tool relevant and operational!

1. **Star the repo ⭐**
2. Fork the Project
3. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
4. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
5. Push to the Branch (`git push origin feature/AmazingFeature`)
6. Open a Pull Request

### **Adding New Providers:**
Edit the `API_LIST` array in `script.js`:
```javascript
{
    "name": "Your Repository",
    "url": "https://your-repo.com/files/<appid>.zip",
    "success_code": 200,
    "enabled": true
}
```

### Requirements:

  * URL must contain <appid> placeholder

  * Must support HTTP HEAD requests

  * Should return 200 for existing files

---

## ⚙️ Technical Details
### The Daisy-Chain Algorithm
LuaMani checks repositories in sequence using HEAD requests:

  1. Verifies file existence via status codes
  2. Retrieves file size from Content-Length headers
  3. Stops immediately upon success
  4. Falls back to next provider on failure

### Multi-Proxy Architecture
Uses 5 different CORS proxies with automatic failover:

  * corsproxy.io → allorigins.win → thingproxy.freeboard.io → etc.

  * Ensures maximum uptime and reliability

  * Automatically switches if a proxy is blocked or slow

### Game Intelligence
  * **Denuvo Detection:** Scans DRM notices in Steam metadata

  * **Online-Only Warning:** Identifies multiplayer-focused games

  * **Genre Tagging:** Extracts and displays game categories

  * **Review Analysis:** Fetches and calculates Steam review scores

---

## ⚠️ Disclaimer
LuaMani is a search indexing tool. It does not host any files. All links are provided by third-party repositories defined in the configuration. Use responsibly. If you notice some non-working code, please report it via the GitHub Issues page.

---

<div align="center">
  
*Thank you for reading*

Made with 💜 by <a href="https://github.com/GOAT42069">GOAT42069</a>

</div> ```
