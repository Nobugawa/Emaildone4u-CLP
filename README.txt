EmailDone4U — Netlify Deployment Package
=========================================
Built: September 2026 — Package v1.15
Domain: emaildone4u.com

WHAT CHANGED THIS PASS (all three HTML files)
--------------------------------------------------
Last pass (v1.14) only fixed intake_form.html's domain-purchase
promise. A broader sweep this time found FOUR more places carrying
the same now-outdated "we'll buy it for you" claim -- all fixed:

  - index.html: FAQ answer to "Do I need to already own a domain?"
    rewritten to explain self-registration + recommend Namecheap.
  - index.html: all THREE pricing cards (Standard/Priority/Rush) listed
    "Domain purchase & configuration" as an included feature -- this
    was the most prominent leftover, a structural pricing-page claim,
    not just FAQ text. Now reads "Domain configuration" (still
    accurate -- you still configure/point DNS, just don't buy it).
  - intake_form.html: the post-submit "What happens next" success
    screen (new-domain branch) still said "We purchase and register
    your domain directly." Rewritten to correctly tell them to
    register it themselves before setup can begin.
  - partners.html: a trust-building bullet said "We purchase or
    configure their domain." Now just "We configure."

A full text sweep for "purchase," "register...for you," and "billed to
you by the registrar" across all three files came back clean after
these fixes -- nothing else found.

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
Edge Function -- see the portal's SETUP_REQUIRED.txt for the one-time
Netlify webhook connection, if not done yet.

VERSIONING
----------
All HTML files in this package share one version number (shown in
each page's footer), relabeled together on every release.

PAGES ARE INTENTIONALLY SEPARATE
---------------------------------
index.html and partners.html have NO links between them.
