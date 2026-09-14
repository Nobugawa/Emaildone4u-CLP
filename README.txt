EmailDone4U — Netlify Deployment Package
=========================================
Built: September 2026
Domain: emaildone4u.com

FILES IN THIS PACKAGE
---------------------
index.html        — B2B landing page (main page, loads at root URL)
partners.html     — Referral partner page (separate audience, no cross-links)
intake_form.html  — Client intake form (linked from index.html)
logo.jpg          — EmailDone4U logo (also embedded in pages as base64)
netlify.toml      — Netlify config (redirects, headers)
README.txt        — This file

DEPLOYING TO NETLIFY
--------------------
1. Go to app.netlify.com
2. Drag this entire folder onto the Netlify drop zone
   OR connect your GitHub repo and set publish directory to "."
3. Go to Site Settings → Domain Management → Add custom domain
4. Enter: emaildone4u.com
5. Follow Netlify's DNS instructions (they give you nameservers or A records)
6. HTTPS is automatic — Netlify provisions SSL within minutes

FORM CAPTURE
------------
Forms are Netlify-native — no Formspree needed.
Once live on Netlify, submissions appear at:
  app.netlify.com → Your site → Forms

Two forms are active:
  - "b2b-intake"      on index.html (B2B client intake)
  - "partner-signup"  on partners.html (partner registration)

Set up email notifications in Netlify:
  Site Settings → Forms → Form notifications → Add notification → Email

PLACEHOLDERS TO REPLACE BEFORE GOING LIVE
------------------------------------------
Search both HTML files for these and swap in real values:
  [YOUR BUSINESS NAME]   → your actual business name
  [Your Phone]           → your phone number (already has help@emaildone4u.com)

UPDATING THE SITE
-----------------
Edit the HTML file locally → re-drag the folder to Netlify
OR if using GitHub: push the updated file and Netlify auto-deploys

PAGES ARE INTENTIONALLY SEPARATE
---------------------------------
index.html and partners.html have NO links between them.
They target different audiences via different outreach channels.
Do not add cross-links between them.
