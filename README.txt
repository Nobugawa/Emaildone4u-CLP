EmailDone4U — Netlify Deployment Package
=========================================
Built: September 2026 (v1.6 — contrast fixes + title tag)
Domain: emaildone4u.com

FILES IN THIS PACKAGE
---------------------
index.html        — B2B landing page (main page, loads at root URL)
partners.html     — Referral partner page (separate audience, no cross-links)
intake_form.html  — Client intake form (unchanged — no edits requested)
images/logo.png   — EmailDone4U logo
netlify.toml      — Netlify config (redirects, headers)
README.txt        — This file

WHAT CHANGED IN THIS PASS (index.html only)
--------------------------------------------
- Fixed the last leftover placeholder: browser tab title was still
  "...| [YOUR BUSINESS NAME]" -> now reads "...| EmailDone4U"
- "Before & After" hero card: background darkened slightly (was pure
  white, blended into the light hero) so it stands out again
- "Passwords ever shared with us" stat card: was a near-invisible
  translucent overlay on the blue band -> now a solid white card with
  a real shadow, text flipped to dark for contrast, green accents
  deepened to read clearly on white
- CTA banner button ("Get My Email Set Up"): was solid blue on a blue
  background (invisible) -> now white with blue text on that section
  specifically; every other blue button on the page is unaffected

FORM DATA FLOW (how submissions actually reach you)
------------------------------------------------------
The intake form is Netlify-native (data-netlify="true") -- when a
client submits it, their browser POSTs the field data directly to
Netlify's servers, which store it and can email you a notification.
Nothing gets sent to the client automatically, and no tech can send
anything "from the portal" today -- that's a separate feature, not yet
built. Two ways to move this forward, not mutually exclusive:
  1. (Already live) Submissions land in Netlify's dashboard under
     Forms, with an optional email notification to you -- your
     always-available manual fallback.
  2. (Buildable, ~30-45 min) A Netlify Function that catches each
     submission via an outgoing webhook and inserts it straight into
     the technician portal's orders table -- so a new lead shows up
     ready to assign, no retyping.

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
