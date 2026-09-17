EmailDone4U — Netlify Deployment Package
=========================================
Built: September 2026 — Package v1.13
Domain: emaildone4u.com

WHAT CHANGED THIS PASS (intake_form.html only)
--------------------------------------------------
New question: "Do you have a website? If so, where's it hosted?"
  - Only shown when the client already owns a domain (or is unsure) --
    skipped entirely for the fresh-purchase path, since there's no
    existing DNS complexity to ask about there.
  - Options cover the common small-business hosts (GoDaddy Website
    Builder, Squarespace, Wix, WordPress, Shopify), a "custom-built"
    catch-all (Netlify/Vercel/Webflow), plus "No website," "Someone
    else manages it for me," and "Not sure."
  - Field name: hosting_platform

WHY THIS MATTERS (read before building the delegation step)
------------------------------------------------------------------
DNS control and domain registration are NOT always the same place.
If a client's website is built on a platform like Netlify, Wix, or
Squarespace and they pointed their domain's nameservers there, DNS
records (including the MX/SPF/DKIM/DMARC records email setup needs)
live on THAT platform, not at the registrar -- the registrar becomes
just a billing/ownership record with zero DNS control. So "where do
we request delegated access" depends on where DNS actually lives, not
just where the domain is registered.

This new field is a strong HINT, not a guarantee -- a site can be
built on Squarespace while DNS still lives at the original registrar
(both models are common). Before sending ANY delegation instructions,
the tech should still confirm live with a nameserver lookup (e.g.
MXToolbox's NS lookup) rather than trusting the client's self-report
as ground truth.

A NOTE ON ACCESS SCOPE (worth knowing, not yet reflected in copy)
------------------------------------------------------------------
Registrars like Namecheap/GoDaddy offer genuinely narrow, DNS-only
delegation -- which is why the "no password, ever" pitch works
cleanly for them. Platform hosts like Netlify don't have an
equivalent narrow "DNS-only" role -- their sharing model is
project/team-based, so getting into DNS there usually means broader
access to the live site (deploys, settings, etc.), not a scoped-down
DNS mailbox. Still categorically true the client's password is never
shared -- just a different, broader shape of access than the
registrar case. Philos's call: mitigate this operationally (vet techs
who'll need host-platform access more carefully than registrar-only
techs) rather than promise something narrower than what's actually
granted.

STILL OPEN (from last pass, unchanged)
------------------------------------------
Whether EmailDone4U continues to purchase/register domains on a
client's behalf (the "No, I need to purchase one" path) is still an
open decision -- see the previous README section on this, carried
forward, not yet resolved.

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
