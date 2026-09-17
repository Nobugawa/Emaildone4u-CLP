EmailDone4U — Netlify Deployment Package
=========================================
Built: September 2026 — Package v1.16
Domain: emaildone4u.com

WHAT CHANGED THIS PASS (all three HTML files)
--------------------------------------------------
Added Google Analytics 4 tracking (the "Google tag" / gtag.js) to all
three pages -- index.html, intake_form.html, partners.html -- right
after <head>, exactly as Google's own installation instructions
specify. Measurement ID: G-7N3S64QL16 (property: Email Done 4 U,
account: Grey Matter Fusion).

Once deployed, traffic should start appearing in GA4 within a few
minutes to hours. Use GA4's own "Test installation" button (visible
on the same admin screen the tag came from) to confirm it's firing
correctly on the live site after deploy.

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
Wired to auto-create orders in the technician portal via a Supabase
Edge Function -- see the portal's SETUP_REQUIRED.txt if not connected yet.

VERSIONING
----------
All HTML files in this package share one version number (shown in
each page's footer), relabeled together on every release.

PAGES ARE INTENTIONALLY SEPARATE
---------------------------------
index.html and partners.html have NO links between them.
