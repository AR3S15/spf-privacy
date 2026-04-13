# spf-privacy
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Privacy Policy — SPF Automation</title>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display:ital@0;1&family=DM+Mono:wght@400;500&family=DM+Sans:wght@300;400;500;600&display=swap" rel="stylesheet" />
  <style>
    :root {
      --bg:         #0b0c10;
      --surface:    #111318;
      --border:     #1d2030;
      --accent:     #f5c518;
      --accent-dim: rgba(245,197,24,.12);
      --text:       #d8dce8;
      --muted:      #656880;
      --heading:    #ffffff;
      --tag-bg:     #16181f;
    }

    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    html { scroll-behavior: smooth; }

    body {
      background: var(--bg);
      color: var(--text);
      font-family: 'DM Sans', sans-serif;
      font-size: 15px;
      line-height: 1.75;
      min-height: 100vh;
    }

    /* ── Subtle grid background ── */
    body::before {
      content: '';
      position: fixed;
      inset: 0;
      background-image:
        linear-gradient(rgba(245,197,24,.025) 1px, transparent 1px),
        linear-gradient(90deg, rgba(245,197,24,.025) 1px, transparent 1px);
      background-size: 48px 48px;
      pointer-events: none;
      z-index: 0;
    }

    /* ── Layout ── */
    .page {
      position: relative;
      z-index: 1;
      max-width: 780px;
      margin: 0 auto;
      padding: 0 24px 80px;
    }

    /* ── Header ── */
    header {
      padding: 56px 0 48px;
      border-bottom: 1px solid var(--border);
      margin-bottom: 52px;
    }

    .brand-row {
      display: flex;
      align-items: center;
      gap: 12px;
      margin-bottom: 24px;
    }

    .brand-pill {
      background: var(--accent);
      color: #000;
      font-family: 'DM Mono', monospace;
      font-size: 9px;
      font-weight: 500;
      letter-spacing: 2.5px;
      text-transform: uppercase;
      padding: 5px 14px;
      border-radius: 3px;
    }

    .version-tag {
      font-family: 'DM Mono', monospace;
      font-size: 10px;
      color: var(--muted);
      letter-spacing: 1px;
      border: 1px solid var(--border);
      padding: 4px 10px;
      border-radius: 3px;
    }

    h1 {
      font-family: 'DM Serif Display', serif;
      font-size: clamp(32px, 5vw, 48px);
      font-weight: 400;
      color: var(--heading);
      line-height: 1.15;
      margin-bottom: 16px;
      letter-spacing: -.5px;
    }

    h1 em {
      font-style: italic;
      color: var(--accent);
    }

    .header-meta {
      display: flex;
      flex-wrap: wrap;
      gap: 20px;
      margin-top: 20px;
    }

    .meta-chip {
      display: flex;
      align-items: center;
      gap: 7px;
      font-size: 12px;
      color: var(--muted);
    }

    .meta-chip .dot {
      width: 6px;
      height: 6px;
      border-radius: 50%;
      background: var(--accent);
      flex-shrink: 0;
    }

    /* ── TOC ── */
    .toc {
      background: var(--surface);
      border: 1px solid var(--border);
      border-left: 3px solid var(--accent);
      border-radius: 6px;
      padding: 24px 28px;
      margin-bottom: 52px;
    }

    .toc-label {
      font-family: 'DM Mono', monospace;
      font-size: 9px;
      letter-spacing: 2.5px;
      text-transform: uppercase;
      color: var(--accent);
      margin-bottom: 14px;
    }

    .toc ol {
      list-style: none;
      counter-reset: toc;
    }

    .toc li {
      counter-increment: toc;
      display: flex;
      align-items: baseline;
      gap: 10px;
      padding: 5px 0;
      border-bottom: 1px solid var(--border);
    }

    .toc li:last-child { border-bottom: none; }

    .toc li::before {
      content: counter(toc, decimal-leading-zero);
      font-family: 'DM Mono', monospace;
      font-size: 10px;
      color: var(--accent);
      flex-shrink: 0;
      width: 22px;
    }

    .toc a {
      font-size: 13px;
      color: var(--text);
      text-decoration: none;
      transition: color .15s;
    }

    .toc a:hover { color: var(--accent); }

    /* ── Sections ── */
    .section {
      margin-bottom: 52px;
      scroll-margin-top: 24px;
    }

    .section-header {
      display: flex;
      align-items: center;
      gap: 14px;
      margin-bottom: 22px;
    }

    .section-num {
      font-family: 'DM Mono', monospace;
      font-size: 10px;
      color: var(--accent);
      background: var(--accent-dim);
      padding: 4px 10px;
      border-radius: 3px;
      flex-shrink: 0;
    }

    h2 {
      font-family: 'DM Serif Display', serif;
      font-size: 22px;
      font-weight: 400;
      color: var(--heading);
      letter-spacing: -.2px;
    }

    p { margin-bottom: 14px; color: var(--text); }
    p:last-child { margin-bottom: 0; }

    /* ── Data table ── */
    .data-table {
      width: 100%;
      border-collapse: collapse;
      margin: 20px 0;
      font-size: 13px;
    }

    .data-table thead tr {
      background: var(--surface);
      border-bottom: 2px solid var(--accent);
    }

    .data-table th {
      padding: 12px 16px;
      text-align: left;
      font-family: 'DM Mono', monospace;
      font-size: 9px;
      letter-spacing: 1.5px;
      text-transform: uppercase;
      color: var(--accent);
      font-weight: 500;
    }

    .data-table td {
      padding: 12px 16px;
      border-bottom: 1px solid var(--border);
      vertical-align: top;
      color: var(--text);
      line-height: 1.5;
    }

    .data-table tr:hover td { background: rgba(255,255,255,.02); }

    .badge {
      display: inline-block;
      font-family: 'DM Mono', monospace;
      font-size: 9px;
      letter-spacing: 1px;
      text-transform: uppercase;
      padding: 3px 8px;
      border-radius: 3px;
      font-weight: 500;
    }

    .badge-yes  { background: rgba(0,214,143,.12); color: #00D68F; }
    .badge-no   { background: rgba(255,107,107,.10); color: #FF6B6B; }
    .badge-opt  { background: rgba(245,197,24,.12);  color: var(--accent); }

    /* ── Info blocks ── */
    .info-block {
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 6px;
      padding: 20px 22px;
      margin: 18px 0;
    }

    .info-block.highlight {
      border-color: var(--accent);
      background: var(--accent-dim);
    }

    .info-block .block-label {
      font-family: 'DM Mono', monospace;
      font-size: 9px;
      letter-spacing: 2px;
      text-transform: uppercase;
      color: var(--accent);
      margin-bottom: 10px;
    }

    /* ── List ── */
    ul.policy-list {
      list-style: none;
      padding: 0;
      margin: 14px 0;
    }

    ul.policy-list li {
      padding: 7px 0 7px 22px;
      position: relative;
      border-bottom: 1px solid var(--border);
      font-size: 14px;
      color: var(--text);
    }

    ul.policy-list li:last-child { border-bottom: none; }

    ul.policy-list li::before {
      content: '→';
      position: absolute;
      left: 0;
      color: var(--accent);
      font-family: 'DM Mono', monospace;
    }

    /* ── Divider ── */
    .divider {
      height: 1px;
      background: linear-gradient(90deg, var(--accent) 0%, var(--border) 40%, transparent 100%);
      margin: 48px 0;
    }

    /* ── Contact card ── */
    .contact-card {
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 8px;
      padding: 28px 32px;
      display: flex;
      flex-wrap: wrap;
      gap: 24px;
      align-items: flex-start;
      justify-content: space-between;
    }

    .contact-card h3 {
      font-family: 'DM Serif Display', serif;
      font-size: 18px;
      color: var(--heading);
      margin-bottom: 8px;
      font-weight: 400;
    }

    .contact-email {
      font-family: 'DM Mono', monospace;
      font-size: 13px;
      color: var(--accent);
      border: 1px solid var(--accent);
      padding: 10px 18px;
      border-radius: 4px;
      text-decoration: none;
      display: inline-block;
      transition: background .15s;
    }

    .contact-email:hover { background: var(--accent-dim); }

    /* ── Footer ── */
    footer {
      border-top: 1px solid var(--border);
      padding-top: 28px;
      margin-top: 60px;
      display: flex;
      flex-wrap: wrap;
      gap: 12px;
      align-items: center;
      justify-content: space-between;
    }

    .footer-brand {
      font-family: 'DM Mono', monospace;
      font-size: 11px;
      color: var(--muted);
      letter-spacing: 1px;
    }

    .footer-note {
      font-size: 11px;
      color: var(--muted);
    }

    /* ── Responsive ── */
    @media (max-width: 600px) {
      header { padding: 36px 0 32px; }
      h1 { font-size: 28px; }
      .contact-card { flex-direction: column; }
      .data-table th, .data-table td { padding: 10px 10px; font-size: 12px; }
    }
  </style>
</head>
<body>
<div class="page">

  <!-- ── HEADER ── -->
  <header>
    <div class="brand-row">
      <span class="brand-pill">SPF Automation</span>
      <span class="version-tag">v5.0</span>
    </div>
    <h1>Privacy <em>Policy</em></h1>
    <div class="header-meta">
      <div class="meta-chip"><span class="dot"></span>Effective Date: April 13, 2026</div>
      <div class="meta-chip"><span class="dot"></span>Last Updated: April 13, 2026</div>
      <div class="meta-chip"><span class="dot"></span>Chrome Extension</div>
    </div>
  </header>

  <!-- ── INTRO ── -->
  <div class="info-block highlight">
    <div class="block-label">Summary</div>
    <p style="margin:0;">
      SPF Automation is a Chrome extension that helps users download images, process Excel files, and search image URLs. We collect only the data strictly necessary to authenticate your account, validate your subscription, and enforce device limits. <strong style="color:#fff;">We never sell your data.</strong>
    </p>
  </div>

  <!-- ── TABLE OF CONTENTS ── -->
  <nav class="toc">
    <div class="toc-label">Contents</div>
    <ol>
      <li><a href="#s1">Who We Are</a></li>
      <li><a href="#s2">Data We Collect</a></li>
      <li><a href="#s3">How We Use Your Data</a></li>
      <li><a href="#s4">Google Account &amp; OAuth</a></li>
      <li><a href="#s5">Subscription &amp; Payment Data</a></li>
      <li><a href="#s6">Device &amp; Session Management</a></li>
      <li><a href="#s7">Data Storage &amp; Retention</a></li>
      <li><a href="#s8">Data Sharing &amp; Third Parties</a></li>
      <li><a href="#s9">Your Rights &amp; Controls</a></li>
      <li><a href="#s10">Security</a></li>
      <li><a href="#s11">Children's Privacy</a></li>
      <li><a href="#s12">Changes to This Policy</a></li>
      <li><a href="#s13">Contact Us</a></li>
    </ol>
  </nav>

  <!-- ── SECTION 1 ── -->
  <section class="section" id="s1">
    <div class="section-header">
      <span class="section-num">01</span>
      <h2>Who We Are</h2>
    </div>
    <p>
      SPF Automation ("we", "our", or "us") is the developer and publisher of the <strong style="color:#fff;">SPF Automation Chrome Extension</strong>, available on the Chrome Web Store. This Privacy Policy explains how we collect, use, store, and protect information when you use our extension.
    </p>
    <p>
      This policy applies to the browser extension itself, the backend licensing service hosted on Cloudflare Workers, and the payment page used to purchase a Pro subscription.
    </p>
  </section>

  <div class="divider"></div>

  <!-- ── SECTION 2 ── -->
  <section class="section" id="s2">
    <div class="section-header">
      <span class="section-num">02</span>
      <h2>Data We Collect</h2>
    </div>
    <p>The table below lists every category of data we collect, why we collect it, and whether collection is required or optional.</p>

    <table class="data-table">
      <thead>
        <tr>
          <th>Data</th>
          <th>Why Collected</th>
          <th>Required?</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td><strong>Gmail Address</strong><br><span style="color:var(--muted);font-size:12px;">e.g. user@gmail.com</span></td>
          <td>Authenticates your identity and links your account to a subscription (1:1 mapping)</td>
          <td><span class="badge badge-yes">Required</span></td>
        </tr>
        <tr>
          <td><strong>Google OAuth Token</strong><br><span style="color:var(--muted);font-size:12px;">Temporary access token</span></td>
          <td>Verified with Google's API to confirm your Gmail identity. Never stored — used once per login.</td>
          <td><span class="badge badge-yes">Required</span></td>
        </tr>
        <tr>
          <td><strong>Device ID</strong><br><span style="color:var(--muted);font-size:12px;">Random 48-char hex string</span></td>
          <td>Generated locally and used to identify your device for the 2-device session limit. Not linked to hardware.</td>
          <td><span class="badge badge-yes">Required</span></td>
        </tr>
        <tr>
          <td><strong>Session Token</strong><br><span style="color:var(--muted);font-size:12px;">Random 64-char hex string</span></td>
          <td>Authorises API requests after login. Stored locally in chrome.storage.local and on our server.</td>
          <td><span class="badge badge-yes">Required</span></td>
        </tr>
        <tr>
          <td><strong>License Key</strong><br><span style="color:var(--muted);font-size:12px;">e.g. SPF-XXXX-XXXX-XXXX</span></td>
          <td>Validates your Pro subscription and binds it to your Gmail address.</td>
          <td><span class="badge badge-yes">Required for Pro</span></td>
        </tr>
        <tr>
          <td><strong>Payment Email</strong><br><span style="color:var(--muted);font-size:12px;">From Razorpay checkout</span></td>
          <td>Stored alongside your license key record to identify the purchaser for support purposes.</td>
          <td><span class="badge badge-opt">Auto-collected</span></td>
        </tr>
        <tr>
          <td><strong>Download Folder Preference</strong></td>
          <td>Saved in chrome.storage.local on your device only. Never sent to our servers.</td>
          <td><span class="badge badge-opt">Optional</span></td>
        </tr>
        <tr>
          <td><strong>Processed Excel Data</strong></td>
          <td>Stored temporarily in chrome.storage.local on your device only. We never see or transmit this data.</td>
          <td><span class="badge badge-no">Local only</span></td>
        </tr>
        <tr>
          <td><strong>Image URLs You Enter</strong></td>
          <td>Processed locally in your browser for download. Never sent to our servers.</td>
          <td><span class="badge badge-no">Local only</span></td>
        </tr>
      </tbody>
    </table>
  </section>

  <div class="divider"></div>

  <!-- ── SECTION 3 ── -->
  <section class="section" id="s3">
    <div class="section-header">
      <span class="section-num">03</span>
      <h2>How We Use Your Data</h2>
    </div>
    <p>We use the data collected for the following purposes only:</p>
    <ul class="policy-list">
      <li><strong>Authentication</strong> — Verifying your Google identity to grant access to the extension</li>
      <li><strong>Subscription validation</strong> — Confirming your license key is valid and active</li>
      <li><strong>1:1 account binding</strong> — Ensuring one Gmail maps to exactly one subscription (and vice versa)</li>
      <li><strong>Device limit enforcement</strong> — Tracking up to 2 concurrent logged-in devices per account</li>
      <li><strong>Session management</strong> — Maintaining and revoking login sessions across devices</li>
      <li><strong>Support</strong> — Using your email to respond to support requests if you contact us</li>
      <li><strong>Abuse prevention</strong> — Detecting and blocking unauthorised sharing of license keys</li>
    </ul>
    <div class="info-block">
      <div class="block-label">What we do NOT do</div>
      <ul class="policy-list">
        <li>We do <strong>not</strong> track, record, or analyse which websites you visit</li>
        <li>We do <strong>not</strong> read the content of pages you browse</li>
        <li>We do <strong>not</strong> collect the image URLs you download or the Excel files you process</li>
        <li>We do <strong>not</strong> use your data for advertising or sell it to any third party</li>
        <li>We do <strong>not</strong> use any analytics or tracking SDK in the extension</li>
      </ul>
    </div>
  </section>

  <div class="divider"></div>

  <!-- ── SECTION 4 ── -->
  <section class="section" id="s4">
    <div class="section-header">
      <span class="section-num">04</span>
      <h2>Google Account &amp; OAuth</h2>
    </div>
    <p>
      SPF Automation uses <strong style="color:#fff;">Google OAuth 2.0</strong> (via the Chrome Identity API) to verify your Gmail address. When you click "Sign in with Google":
    </p>
    <ul class="policy-list">
      <li>Chrome displays a standard Google consent screen — you decide whether to proceed</li>
      <li>We request only the <strong>email</strong>, <strong>openid</strong>, and <strong>profile</strong> OAuth scopes — the minimum needed to identify you</li>
      <li>The OAuth access token is sent to our backend <strong>once</strong> to extract your email address, then discarded — it is never logged or stored</li>
      <li>We do <strong>not</strong> access your Gmail messages, Google Drive, Calendar, Contacts, or any other Google service</li>
      <li>You can revoke our access at any time at <a href="https://myaccount.google.com/permissions" target="_blank" style="color:var(--accent);">myaccount.google.com/permissions</a></li>
    </ul>
    <p>
      Our use of Google user data complies with the
      <a href="https://developers.google.com/terms/api-services-user-data-policy" target="_blank" style="color:var(--accent);">Google API Services User Data Policy</a>,
      including the Limited Use requirements.
    </p>
  </section>

  <div class="divider"></div>

  <!-- ── SECTION 5 ── -->
  <section class="section" id="s5">
    <div class="section-header">
      <span class="section-num">05</span>
      <h2>Subscription &amp; Payment Data</h2>
    </div>
    <p>
      Payments are processed by <strong style="color:#fff;">Razorpay</strong>. We do not collect or store your credit card number, UPI details, or any other payment instrument data — Razorpay handles all of this directly under their own
      <a href="https://razorpay.com/privacy/" target="_blank" style="color:var(--accent);">Privacy Policy</a>.
    </p>
    <p>
      After a successful payment, Razorpay sends a webhook to our server containing:
    </p>
    <ul class="policy-list">
      <li>Your <strong>email address</strong> (as entered during checkout)</li>
      <li>The <strong>Razorpay Payment ID</strong> and <strong>Order ID</strong> (for support and dispute resolution)</li>
    </ul>
    <p>
      We use this data solely to generate and associate your license key. It is stored in our Cloudflare KV database and is not shared with any other party.
    </p>
  </section>

  <div class="divider"></div>

  <!-- ── SECTION 6 ── -->
  <section class="section" id="s6">
    <div class="section-header">
      <span class="section-num">06</span>
      <h2>Device &amp; Session Management</h2>
    </div>
    <p>
      To enforce the <strong style="color:#fff;">2-device concurrent login limit</strong>, we store and manage session records as follows:
    </p>

    <div class="info-block">
      <div class="block-label">What is stored per session</div>
      <ul class="policy-list">
        <li><strong>Device ID</strong> — a random string generated by your browser. It does not identify your hardware, browser fingerprint, IP address, or physical location.</li>
        <li><strong>Session Token</strong> — a cryptographically random 64-character hex string used to authenticate requests</li>
        <li><strong>Login Timestamp</strong> — when the session was created</li>
        <li><strong>Last Seen Timestamp</strong> — updated each time the extension validates its session</li>
      </ul>
    </div>

    <p>
      If you attempt to log in on a third device, you will be shown a screen listing your 2 active devices and given the option to sign out of one remotely. No action is taken automatically — you remain in control.
    </p>
    <p>
      Sessions are deleted from our servers when you sign out, or when an admin revokes your subscription. You can also sign out of individual devices from the Settings panel inside the extension.
    </p>
  </section>

  <div class="divider"></div>

  <!-- ── SECTION 7 ── -->
  <section class="section" id="s7">
    <div class="section-header">
      <span class="section-num">07</span>
      <h2>Data Storage &amp; Retention</h2>
    </div>

    <table class="data-table">
      <thead>
        <tr>
          <th>Data</th>
          <th>Where Stored</th>
          <th>Retention</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>Gmail address + subscription binding</td>
          <td>Cloudflare KV (global edge)</td>
          <td>Until you request deletion or your subscription is revoked</td>
        </tr>
        <tr>
          <td>Session tokens + device IDs</td>
          <td>Cloudflare KV + chrome.storage.local</td>
          <td>Until logout or subscription revocation</td>
        </tr>
        <tr>
          <td>License key records</td>
          <td>Cloudflare KV</td>
          <td>Indefinitely (for support and dispute resolution)</td>
        </tr>
        <tr>
          <td>Download folder preference</td>
          <td>chrome.storage.local (your device)</td>
          <td>Until you uninstall the extension</td>
        </tr>
        <tr>
          <td>Processed Excel data</td>
          <td>chrome.storage.local (your device)</td>
          <td>Until you clear the cache within the extension</td>
        </tr>
        <tr>
          <td>Payment email + Razorpay IDs</td>
          <td>Cloudflare KV</td>
          <td>Until you request deletion</td>
        </tr>
      </tbody>
    </table>

    <p>
      Cloudflare's infrastructure is distributed globally. Data stored in Cloudflare KV may be replicated across their edge network. Cloudflare's data practices are governed by their
      <a href="https://www.cloudflare.com/privacypolicy/" target="_blank" style="color:var(--accent);">Privacy Policy</a>.
    </p>
  </section>

  <div class="divider"></div>

  <!-- ── SECTION 8 ── -->
  <section class="section" id="s8">
    <div class="section-header">
      <span class="section-num">08</span>
      <h2>Data Sharing &amp; Third Parties</h2>
    </div>
    <p>We share your data with the following third parties, and no others:</p>

    <table class="data-table">
      <thead>
        <tr>
          <th>Third Party</th>
          <th>Purpose</th>
          <th>Data Shared</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td><strong>Google</strong><br><span style="color:var(--muted);font-size:11px;">OAuth identity</span></td>
          <td>Verifying your Gmail identity during login</td>
          <td>OAuth access token (sent to Google's tokeninfo API)</td>
        </tr>
        <tr>
          <td><strong>Razorpay</strong><br><span style="color:var(--muted);font-size:11px;">Payment processing</span></td>
          <td>Processing subscription payments</td>
          <td>Email, payment amount. No card data touches our servers.</td>
        </tr>
        <tr>
          <td><strong>Cloudflare</strong><br><span style="color:var(--muted);font-size:11px;">Backend infrastructure</span></td>
          <td>Hosting our Workers backend and KV database</td>
          <td>All server-side data passes through Cloudflare's network</td>
        </tr>
      </tbody>
    </table>

    <p>
      We do <strong>not</strong> share your data with advertisers, data brokers, analytics companies, or any other third party not listed above. We do not sell your personal information.
    </p>
  </section>

  <div class="divider"></div>

  <!-- ── SECTION 9 ── -->
  <section class="section" id="s9">
    <div class="section-header">
      <span class="section-num">09</span>
      <h2>Your Rights &amp; Controls</h2>
    </div>
    <p>You have full control over your data. You can exercise the following rights at any time by contacting us:</p>
    <ul class="policy-list">
      <li><strong>Access</strong> — Request a copy of all data we hold about your Gmail address</li>
      <li><strong>Correction</strong> — Ask us to correct inaccurate records</li>
      <li><strong>Deletion</strong> — Request deletion of your account data, binding, and sessions. Note: license key purchase records may be retained for financial compliance.</li>
      <li><strong>Session revocation</strong> — Sign out of any or all devices directly from within the extension (Settings → Account → Active Devices)</li>
      <li><strong>Google access revocation</strong> — Revoke our OAuth access at <a href="https://myaccount.google.com/permissions" target="_blank" style="color:var(--accent);">myaccount.google.com/permissions</a> at any time</li>
      <li><strong>Uninstall</strong> — Uninstalling the extension removes all locally stored data (chrome.storage.local) immediately</li>
    </ul>
    <div class="info-block">
      <div class="block-label">How to delete your account data</div>
      <p style="margin:0;">Email us at the address in Section 13 with the subject line <strong style="color:#fff;">"Data Deletion Request"</strong> and include your Gmail address. We will process your request within 30 days.</p>
    </div>
  </section>

  <div class="divider"></div>

  <!-- ── SECTION 10 ── -->
  <section class="section" id="s10">
    <div class="section-header">
      <span class="section-num">10</span>
      <h2>Security</h2>
    </div>
    <p>We implement the following technical measures to protect your data:</p>
    <ul class="policy-list">
      <li>All communication between the extension and our backend uses <strong>HTTPS / TLS</strong></li>
      <li>Session tokens are cryptographically random 256-bit values generated using the Web Crypto API</li>
      <li>Google OAuth tokens are verified server-side and never logged or stored</li>
      <li>Razorpay webhook authenticity is verified using <strong>HMAC-SHA256 signatures</strong> before processing</li>
      <li>Admin endpoints require a secret key transmitted via a request header</li>
      <li>No sensitive credentials are hardcoded in the extension source code</li>
    </ul>
    <p>
      Despite these measures, no system is 100% secure. If you believe you have found a security vulnerability, please contact us privately before disclosing it publicly.
    </p>
  </section>

  <div class="divider"></div>

  <!-- ── SECTION 11 ── -->
  <section class="section" id="s11">
    <div class="section-header">
      <span class="section-num">11</span>
      <h2>Children's Privacy</h2>
    </div>
    <p>
      SPF Automation is not directed at children under the age of 13 (or 16 in the European Economic Area). We do not knowingly collect personal information from children. If you believe a child has provided us with personal data, please contact us immediately and we will delete it promptly.
    </p>
  </section>

  <div class="divider"></div>

  <!-- ── SECTION 12 ── -->
  <section class="section" id="s12">
    <div class="section-header">
      <span class="section-num">12</span>
      <h2>Changes to This Policy</h2>
    </div>
    <p>
      We may update this Privacy Policy from time to time. When we do, we will update the "Last Updated" date at the top of this page. For significant changes, we will notify users via a notice in the extension or by email.
    </p>
    <p>
      Your continued use of SPF Automation after any changes constitutes your acceptance of the revised policy. We encourage you to review this page periodically.
    </p>
  </section>

  <div class="divider"></div>

  <!-- ── SECTION 13 ── -->
  <section class="section" id="s13">
    <div class="section-header">
      <span class="section-num">13</span>
      <h2>Contact Us</h2>
    </div>
    <p>
      If you have any questions about this Privacy Policy, want to exercise your data rights, or need support, please reach out:
    </p>
    <div class="contact-card">
      <div>
        <h3>SPF Automation</h3>
        <p style="font-size:13px;color:var(--muted);margin-top:4px;">We aim to respond within 2 business days.</p>
      </div>
      <a class="contact-email" href="mailto:support@spfautomation.com">
        support@spfautomation.com
      </a>
    </div>
  </section>

  <!-- ── FOOTER ── -->
  <footer>
    <span class="footer-brand">SPF AUTOMATION · PRIVACY POLICY</span>
    <span class="footer-note">Effective April 13, 2026 · Version 5.0</span>
  </footer>

</div>
</body>
</html>
