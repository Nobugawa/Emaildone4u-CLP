EmailDone4U — Netlify Deployment Package
=========================================
Built: September 2026 — Package v1.11
Domain: emaildone4u.com

WHAT CHANGED THIS PASS (intake_form.html only)
--------------------------------------------------
1. Clarified the existing aliases field so it can't be mistaken for
   separate logins: "Additional addresses that forward to this same
   inbox? (not separate logins)"

2. Added one new field, no explanation attached (kept deliberately
   simple to avoid form-abandonment risk): "Does anyone else on your
   team need their own separate email login?" Yes/No, with the hint
   "extra cost — we'll go over pricing when we follow up." No pricing,
   no alias-vs-mailbox education anywhere in the form itself -- all of
   that nuance is deferred to your personal follow-up conversation,
   same pattern already used for domain naming.

STILL AN OPEN DECISION (not yet acted on)
---------------------------------------------
The flat add-on fee for a separate mailbox has not been set anywhere
in code or copy -- by design, since Philos wants that number decided
and quoted personally per lead, not published. Nothing to change here
until/unless that changes.

DEPLOYING TO NETLIFY
--------------------
1. Go to app.netlify.com
2. Drag this entire folder onto the Netlify drop zone
   OR connect your GitHub repo and set publish directory to "."
3. Site Settings -> Domain Management -> Add custom domain -> emaildone4u.com
4. HTTPS is automatic -- Netlify provisions SSL within minutes

FORM CAPTURE
------------
One active form: "email-setup-intake" on intake_form.html.
Submissions appear at: app.netlify.com -> Your site -> Forms

VERSIONING
----------
All HTML files in this package share one version number (shown in
each page's footer), relabeled together on every release.

PAGES ARE INTENTIONALLY SEPARATE
---------------------------------
index.html and partners.html have NO links between them.
