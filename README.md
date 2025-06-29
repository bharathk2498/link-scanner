# Malicious Link Scanner 🛡️

A simple, client-side web application to analyze URLs for common signs of phishing or malware. This tool is for educational purposes and provides a basic first-pass check on a suspicious link.

## Features

- **Protocol Check**: Verifies if the link uses secure HTTPS.
- **Blacklist Check**: Checks against a small, hardcoded list of known malicious domains.
- **IP Address Detection**: Flags URLs that use an IP address instead of a domain name.
- **URL Shortener Detection**: Warns if a common URL shortener is used, which can obscure the final destination.
- **Suspicious Keyword Analysis**: Looks for keywords often found in phishing URLs (e.g., "login", "verify").

## How to Deploy on GitHub Pages

You can host this scanner for **free** on GitHub Pages in 5 easy steps:

1.  **Create a new Repository:** Create a new public repository on GitHub. You can name it `link-scanner`.
2.  **Upload Files:** Add the `index.html`, `style.css`, and `script.js` files to this new repository.
3.  **Go to Settings:** In your repository's main page, click on the **"Settings"** tab.
4.  **Navigate to Pages:** In the left sidebar of the Settings page, click on **"Pages"**.
5.  **Set the Source:** Under "Build and deployment," select **"Deploy from a branch"** as the source. Choose the `main` branch and the `/ (root)` folder, then click **"Save"**.

That's it! GitHub will publish your site and provide you with the public URL. It may take a minute or two to go live.

## Disclaimer

This is a basic tool and should not be considered a foolproof security solution. Always exercise caution and use comprehensive security software.
