EmailDone4U — Netlify Deployment Package
=========================================
Built: September 2026 — Package v1.8 (all files now share ONE version
number, not per-file numbers — see "VERSIONING" below)
Domain: emaildone4u.com

FILES IN THIS PACKAGE
---------------------
index.html        — B2B landing page (main page, loads at root URL)
partners.html     — Referral partner page (separate audience, no cross-links)
intake_form.html  — The real client intake form
images/logo.png   — EmailDone4U logo
netlify.toml      — Netlify config (redirects, headers)
README.txt        — This file

VERSIONING (changed this pass)
--------------------------------
Previously index.html and intake_form.html incremented separately
(v1.7 and v1.4), which didn't make sense for one package. From now on
every HTML file in this package shares one version number, shown in
each page's footer -- this release is v1.8 for all three files, even
though partners.html's content did not change this pass. If only one
file changes in a future release, all three still get relabeled to
the new shared number so the footer badge is never ambiguous about
which release you're looking at.

WHAT CHANGED THIS PASS
-------------------------
1. Fixed the intake form's leftover footer placeholder:
   "[YOUR BUSINESS NAME] · [Your Phone] · [your@email.com]"
   -> now shows the real logo and help@emaildone4u.com (no phone,
   as requested -- not needed at this time).

2. Fixed the intake form's Netlify form name to match what actually
   shows in your Netlify dashboard: "email-setup-intake" (previously
   called "b2b-intake" on the old, now-removed popup).

3. THE IMPORTANT FIX -- the post-submit "What happens next" list was
   still saying "We send you two secure invitation links... you click
   accept" for every single submission, regardless of what the person
   actually answered on "Do you already own this domain?". That's
   backwards for anyone who already owns a domain -- THEY need to go
   grant US access through their own registrar account; we don't send
   them a link to click. The success screen is now dynamic and shows
   the genuinely correct next steps based on their actual answer:
     - Already own a domain -> explains the registrar access-granting
       step accurately (2-3 minutes, on their end, no password)
     - Buying a new domain / unsure -> explains that we handle the
       domain purchase directly, nothing needed from them there
   Both versions correctly describe that Google Workspace billing is
   entered directly by them on Google's own page, never shared with us.

A NOTE ON THE NETLIFY DASHBOARD
-----------------------------------
If the top-level Forms summary in Netlify's dashboard looks like it
shows nothing at a glance, that's a Netlify display quirk, not a sign
submissions aren't arriving -- click into the "email-setup-intake"
form itself to see actual verified submissions. This was confirmed
working end-to-end during testing (a real submission with every field
captured correctly was verified in the dashboard).

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
One active form: "email-setup-intake" on intake_form.html.
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
