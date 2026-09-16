EmailDone4U — Netlify Deployment Package
=========================================
Built: September 2026 (v1.7 index.html / v1.4 intake_form.html)
Domain: emaildone4u.com

FILES IN THIS PACKAGE
---------------------
index.html        — B2B landing page (main page, loads at root URL)
partners.html     — Referral partner page (separate audience, no cross-links)
intake_form.html  — THE real client intake form (see below — now fixed)
images/logo.png   — EmailDone4U logo
netlify.toml      — Netlify config (redirects, headers)
README.txt        — This file

*** IMPORTANT: A REAL BUG WAS FOUND AND FIXED THIS PASS ***
--------------------------------------------------------------
intake_form.html previously had NO working submission. Its "Submit"
button showed a fake "You're all set!" success screen but never sent
the data anywhere -- Netlify, email, nowhere. Anyone who filled it out
believed they'd reached you; you would never have received it. This is
now fixed:
  - The form is properly wired to Netlify Forms (name="email-setup-intake")
  - Every field now has a proper `name` attribute so Netlify actually
    captures it (several fields only had an `id` before, which Netlify
    ignores)
  - The submit handler now actually POSTs the data before showing success

ONE INTAKE PATH NOW, NOT TWO
------------------------------
Previously, index.html's "Get Started" buttons opened a separate, shallow
4-field popup (name/business/email/phone) that duplicated intake_form.html
badly -- two different forms, two different success messages, neither one
clearly "the real one." That popup has been removed entirely. Every
"Get Started" button on index.html now links straight to intake_form.html,
which is the single, comprehensive intake going forward. The three
pricing-tier buttons pre-select the matching tier on that page via a
URL parameter (?tier=standard|priority|rush).

PROCESS COPY MADE ACCURATE
-----------------------------
The old copy implied the client "just clicks a secure invitation link"
for both domain and Google Workspace access -- inaccurate for anyone who
already owns a domain, since registrar delegation (Namecheap "Sharing &
Transfer", GoDaddy "Delegate Access") requires navigating their own
account settings, not clicking one link. Rewritten in two places (the
"No Password" section and the "How It Works" steps) to accurately say:
  - Domain access is only needed if they already own a domain -- a short
    guided task (2-3 min) using instructions/video you send, not a
    single click. Buying a new domain instead means no client action
    on the domain side at all.
  - Google Workspace needs no login sharing whatsoever -- the client
    enters their own payment card directly on Google's own page when
    it's time to activate billing.
The "no password, ever" claim remains fully true either way -- this
just stops overstating HOW simple the domain step is when it applies.

OTHER FIXES THIS PASS
------------------------
- Hero tagline "Setup takes less than a day" removed -- misleading,
  since Standard tier is 2 business days. Now: "You never share a
  password — no matter which setup speed you choose."
- Fixed intake_form.html's own leftover title placeholder
  ("...| [YOUR BUSINESS NAME]" -> "...| EmailDone4U")
- Contrast fixes: Before/After hero tile darkened more decisively
  (was barely distinguishable from the page background); "Passwords
  ever shared with us" stat card fixed a prior pass ago; "Still using
  Gmail" section background darkened and the big "85%" numeral color
  deepened so it's actually visible; CTA banner button is white so it
  doesn't disappear into the blue band.

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
One active form now: "email-setup-intake" on intake_form.html.
(partners.html's "partner-signup" form is separate and unaffected.)
Submissions appear at: app.netlify.com -> Your site -> Forms
Set up email notifications: Site Settings -> Forms -> Form notifications

UPDATING THE SITE
-----------------
Edit the HTML file locally -> re-drag the folder to Netlify
OR if using GitHub: push the updated file and Netlify auto-deploys

PAGES ARE INTENTIONALLY SEPARATE
---------------------------------
index.html and partners.html have NO links between them.
They target different audiences via different outreach channels.
Do not add cross-links between them.
