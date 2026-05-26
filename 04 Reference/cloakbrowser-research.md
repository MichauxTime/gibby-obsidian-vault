# CloakBrowser

## What it is
A stealth Chromium browser with 58 source-level C++ fingerprint patches that passes bot detection systems (Cloudflare Turnstile, FingerprintJS, reCAPTCHA v3 0.9 score) — a drop-in Playwright/Puppeteer replacement for Python and JavaScript.

## The good
- Patches at the C++ source level, not JS injection — survives Chrome updates that break playwright-stealth and undetected-chromedriver
- humanize=True flag adds Bezier curve mouse movement, per-character keyboard timing, and realistic scroll — one flag covers behavioral detection
- pip install / npm install auto-downloads binary; zero config to get started
- Free and open source (MIT-ish license); no subscriptions, no usage limits
- Ships a self-hosted Browser Profile Manager as a Multilogin/GoLogin alternative via Docker + noVNC
- Chromium 146 base; SOCKS5 + HTTP proxy support including inline credentials and WebRTC IP spoofing

## The bad
- ~200MB binary download on first run — not a lightweight dependency
- Keeping up with Chromium releases means the stealth build can lag; detection windows exist between upstream Chromium release and patch rebuild
- The Manager (multi-profile) is a separate repo — not a single unified install

## Watch out for
- Using this against sites' ToS constitutes unauthorized access in many jurisdictions — clear legal review needed before using on any commercial scraping workflow
- Auto-updating binary means you're trusting CloakHQ's build pipeline; review their release signing process before using in production

## Top 5 use cases for us (Gibby/StreetLegal/Stylograph context)
1. Scraping permit portals and municipal databases that block headless browsers for StreetLegal jurisdiction research
2. Automating Stylograph outreach workflows that require browser-based form submissions to institutions with bot detection
3. Monitoring competitor pricing pages or application portals that serve different content to bots vs. humans
4. Testing Stylograph and StreetLegal web properties against fingerprinting/bot detection to identify what real users see vs. what scrapers see
5. Replacing current Playwright setup in the social pipeline render workflow if bot detection becomes an issue with social platforms

## Verdict
Adopt for internal research scraping — the source-level approach is the right architecture and the free/open license removes cost friction; just enforce ToS review before pointing it at any target.

## Source
https://github.com/CloakHQ/CloakBrowser
