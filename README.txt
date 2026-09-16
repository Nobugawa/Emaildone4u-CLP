EmailDone4U — Netlify Deployment Package
=========================================
Built: September 2026 (v1.5 — aesthetic pass)
Domain: emaildone4u.com

FILES IN THIS PACKAGE
---------------------
index.html        — B2B landing page (main page, loads at root URL)
partners.html     — Referral partner page (separate audience, no cross-links)
intake_form.html  — Client intake form (linked from index.html)
images/logo.png   — EmailDone4U logo
netlify.toml      — Netlify config (redirects, headers)
README.txt        — This file

WHAT CHANGED IN THIS PASS (index.html only)
--------------------------------------------
Matched the aesthetic direction of emc2digital.com:
- Header (nav bar): was filled dark navy -> now white, with dark text/links
- Footer: was near-black -> now white, with a light top border
- Logo: enlarged in both header (30px->46px) and footer (24px->34px)
- Hero section: was solid dark-navy fill -> now a light gradient
  background with navy text, matching EMC2's mostly-white feel
- "No password" section and the closing CTA banner: toned down from
  near-black navy to a richer-but-lighter medium blue band (matching
  the "Digital Systems Snapshot" band style on emc2digital.com) --
  kept as bolder accent sections rather than flattened to white, since
  they're doing real visual work (trust-building, call to action)
- "Priority" pricing card: was a solid dark-navy card -> now a light
  blue-tinted card with a blue border, consistent with the rest
- Font and page content are unchanged throughout

partners.html and intake_form.html were NOT touched in this pass --
they still reflect the pre-v1.5 dark-navy styling. Say the word if you
want the same treatment carried over to those pages too.

DEPLOYING TO NETLIFY
--------------------
1. Go to app.netlify.com
2. Drag this entire folder onto the Netlify drop zone
   OR connect your GitHub repo and set publish directory to "."
3. Go to Site Settings -> Domain Management -> Add custom domain
4. Enter: emaildone4u.com
5. Follow Netlify's DNS instructions (they give you nameservers or A records)
6. HTTPS is automatic -- Netlify provisions SSL within minutes

FORM CAPTURE
------------
Forms are Netlify-native -- no Formspree needed.
Once live on Netlify, submissions appear at:
  app.netlify.com -> Your site -> Forms

Two forms are active:
  - "b2b-intake"      on index.html (B2B client intake)
  - "partner-signup"  on partners.html (partner registration)

Set up email notifications in Netlify:
  Site Settings -> Forms -> Form notifications -> Add notification -> Email

UPDATING THE SITE
-----------------
Edit the HTML file locally -> re-drag the folder to Netlify
OR if using GitHub: push the updated file and Netlify auto-deploys

PAGES ARE INTENTIONALLY SEPARATE
---------------------------------
index.html and partners.html have NO links between them.
They target different audiences via different outreach channels.
Do not add cross-links between them.
