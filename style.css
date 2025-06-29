document.addEventListener('DOMContentLoaded', () => {
    const urlInput = document.getElementById('urlInput');
    const scanBtn = document.getElementById('scanBtn');
    const analysisList = document.getElementById('analysisList');

    // For demonstration: a small list of known malicious domains.
    const maliciousDomains = ['evil-site.com', 'phishing-central.net', 'malware-hub.org'];

    scanBtn.addEventListener('click', () => {
        const urlString = urlInput.value.trim();
        if (!urlString) {
            alert('Please enter a URL.');
            return;
        }

        // Clear previous results
        analysisList.innerHTML = '';

        try {
            const url = new URL(urlString.startsWith('http') ? urlString : `http://${urlString}`);
            
            // 1. Check Protocol (HTTPS is preferred)
            const protocol = url.protocol;
            addResult(
                protocol === 'https:' ? 'Safe' : 'Warning',
                `Protocol is ${protocol.slice(0, -1).toUpperCase()}`,
                `Secure HTTPS is used.`,
                `Unencrypted HTTP is used. Data may be visible to attackers.`
            );

            // 2. Check for known malicious domains
            const isMalicious = maliciousDomains.some(domain => url.hostname.includes(domain));
            addResult(
                isMalicious ? 'Danger' : 'Safe',
                `Domain Reputation`,
                `Domain is not on our basic blacklist.`,
                `Domain found on a known malicious list!`
            );

            // 3. Check for IP address as hostname
            const ipRegex = /^\d{1,3}\.\d{1,3}\.\d{1,3}\.\d{1,3}$/;
            const isIpAddress = ipRegex.test(url.hostname);
            addResult(
                isIpAddress ? 'Danger' : 'Safe',
                `URL uses Domain Name`,
                `Using a domain name is standard practice.`,
                `Using an IP address can hide the true destination and is a common phishing tactic.`
            );

            // 4. Check for URL Shorteners (basic check)
            const shorteners = ['bit.ly', 't.co', 'tinyurl.com'];
            const isShortener = shorteners.some(short => url.hostname.includes(short));
             addResult(
                isShortener ? 'Warning' : 'Safe',
                `URL Shortener Check`,
                `No common URL shortener detected.`,
                `URL shorteners can hide the final destination. Be extra cautious.`
            );
            
            // 5. Check for suspicious keywords in the path or query
            const suspiciousKeywords = ['login', 'verify', 'account', 'update', 'secure'];
            const hasSuspiciousKeywords = suspiciousKeywords.some(kw => url.pathname.includes(kw) || url.search.includes(kw));
            addResult(
                hasSuspiciousKeywords ? 'Warning' : 'Safe',
                `Suspicious Keywords`,
                `No common suspicious keywords found in the URL path.`,
                `URL contains keywords often used in phishing attacks.`
            );

        } catch (error) {
            analysisList.innerHTML = ''; // Clear again on error
            addResult(
                'Danger',
                'Invalid URL',
                '',
                `The entered text could not be parsed as a valid URL.`
            );
        }
    });

    function addResult(status, title, safeMessage, riskMessage) {
        const listItem = document.createElement('li');
        let icon = '✅';
        let message = safeMessage;
        let statusClass = 'status-safe';

        if (status === 'Warning') {
            icon = '⚠️';
            message = riskMessage;
            statusClass = 'status-warn';
        } else if (status === 'Danger') {
            icon = '❌';
            message = riskMessage;
            statusClass = 'status-danger';
        }
        
        listItem.className = statusClass;
        listItem.innerHTML = `<span class="icon">${icon}</span> <strong>${title}:</strong> ${message}`;
        analysisList.appendChild(listItem);
    }
});
