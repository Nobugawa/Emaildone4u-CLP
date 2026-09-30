EmailDone4U — Netlify Deployment Package
=========================================
Built: September 2026 — Package v1.24
Domain: emaildone4u.com

WHAT CHANGED THIS PASS (v1.24)
--------------------------------------------------
index.html only (plus version labels V1.24 on all pages):
1. The "Curious about the technical details?" expander in the security
   section (blue background) is now a light/white card with dark text, so it
   stands out instead of blending into the blue.
2. Step 3 ("We configure everything") now has a "What exactly do we set up?"
   link that opens a new expander below the four steps, in plain language
   first with the technical terms (MX, SPF, DKIM, DMARC) explained inline.
Also includes v1.23 (sitemap.xml and robots.txt). Submit sitemap.xml in
Google Search Console > Sitemaps.

WHAT CHANGED IN v1.23 (also included)
--------------------------------------------------
Added sitemap.xml (home, intake form, privacy, terms) and robots.txt
(allows crawling and points to the sitemap). partners.html is deliberately
NOT in the sitemap and NOT blocked in robots.txt, so Google can read its
noindex tag. Version labels bumped to V1.23 on all pages. Nothing else
changed. In Google Search Console > Sitemaps, submit: sitemap.xml

WHAT CHANGED IN v1.22 (also included)
--------------------------------------------------
intake_form.html now sends a GA4 "generate_lead" event when the form is
submitted (with tier and domain_status parameters), so Google Ads has a
real conversion to optimize toward. Nothing else changed. Setup:
GA4 Admin > Events > mark generate_lead as a key event, then Google Ads >
Goals > Conversions > Import from GA4.

WHAT CHANGED IN v1.21 (also included)
--------------------------------------------------
partners.html now has <meta name="robots" content="noindex, nofollow"> so
Google Search will not list the referral-partner page. It stays reachable
by direct link (noindex is NOT password protection). Nothing else changed.
No other page links to partners.html; keep it that way. Do not add
partners.html to a sitemap and do not block it in robots.txt (Google must
be able to read the noindex tag).

WHAT CHANGED IN v1.20 (also included)
--------------------------------------------------
Version-label correction only. The #tier anchor on intake_form.html
(section 4, id="tier") was added AFTER v1.19 was first delivered, so it
is relabeled v1.20 to keep one change = one version. No other changes.
Use /intake_form?tier=rush#tier as the Google Ads "Same-Day Setup"
sitelink URL. Anything listed under v1.19 below is also included.

WHAT CHANGED IN v1.19 (also included)
--------------------------------------------------
1. New "Who We Are" section on index.html (id="about") with Philos's photo
   (images/philos-kim.jpg), founder title, phone and email. Deliberately
   avoids "solo" / "one-person" wording so it still reads correctly if
   techs are added later. The "about ten years running businesses" line
   comes from what Philos told us -- edit or remove as desired.
2. New privacy.html and terms.html (served at /privacy and /terms via
   Netlify pretty URLs). Linked from all three pages' footers and from
   the intake form's submit area. DRAFTS -- have an attorney review.
   Items to confirm: payment due-date wording, "we may remove DNS
   records if unpaid" clause, cancellation wording, NJ governing law.
3. Footer on all pages: "EmailDone4U is a service of Grey Matter Fusion
   Inc. - Riverdale, NJ - 973-888-3208". Street address and EIN are
   intentionally NOT shown.
4. (Added late; shipped as v1.20) Intake form section 4 has id="tier". A link to
   /intake_form?tier=rush#tier lands directly on the tier tiles with Rush
   pre-selected (use this as the Google Ads "Same-Day Setup" sitelink URL).
   The pricing-card buttons still go to the top of the form on purpose.
5. Stripe mention (text only) in the pay-after fine print. If adding
   Stripe's badge image, use only the official asset from Stripe's brand
   assets page and follow its usage guidelines.

WHAT CHANGED LAST PASS (v1.18)
--------------------------------------------------
1. De-geeked index.html (inline-expand approach): DNS/SPF/DKIM/DMARC removed
   from default copy (hero, security steps, how-it-works, pricing bullets,
   FAQ). All technical detail now lives in ONE collapsed "Curious about the
   technical details?" expander in the Security section. partners.html is a
   different audience and was left as-is (version number only).
2. Pay-after messaging: new "Pay only when it works" section (id="pay-after")
   between Pricing and FAQ, a hero pill, a pricing subline, a "When do I
   pay?" FAQ, and matching lines on the intake form + every success screen.
   Wording covers OUR setup fee only; Google's ~$7/mo is billed by Google.
3. Intake form domain flow rebuilt (intake_form.html):
   - Three clear paths: Yes / I'm not sure / No, I need to get one.
   - Domain field moved into section 2 and relabeled per path.
   - "Not sure": domain field is OPTIONAL (may arrive blank in the portal),
     hosting question still shown.
   - "No": tells them they can submit before buying; we start once it's theirs.
   - Registrar pills gained "Not sure". Field names unchanged, so the
     Netlify->Supabase webhook mapping is unaffected.
   - Success screen now has three variants (yes / unsure / no); previously
     "unsure" wrongly showed the "register first" steps.
4. Sitelink anchors verified present: #how, #pricing, #faq, #pay-after.

WHAT CHANGED LAST PASS (v1.17, all three HTML files)
--------------------------------------------------
1. Fixed copy on index.html that unintentionally implied we buy/register
   domains for clients (contradicts the no-domain-purchase policy):
   - "Security First" section, step 1: no longer says "we handle it on
     our end" for a new domain -- now says the client registers it
     themselves first, pointing to the domain FAQ.
   - "Done in four steps" section, step 2: same fix.
   - "Done in four steps" step 3: "Domain, Google Workspace, SPF..."
     changed to "DNS records, Google Workspace, SPF..." -- was implying
     we take ownership of/handle the domain itself, when we only
     configure DNS records on a domain the client already owns.
2. Made clear (as requested) that our access is TEMPORARY:
   - Security section subhead and step 1 heading now say "temporary"
     explicitly.
   - Checklist bullet: "Delegated access" -> "Temporary delegated access".
3. Domain FAQ answer now recommends three registrars with links
   (Namecheap as primary recommendation, GoDaddy, Squarespace Domains)
   instead of just naming Namecheap in passing.
4. Added a real favicon across all three pages (previously none existed
   -- browser tabs were showing the generic blank-page icon). Built from
   the envelope+checkmark mark cropped out of images/logo.png:
   /favicon.ico, /favicon.svg, /images/favicon-16x16.png,
   /images/favicon-32x32.png, /images/apple-touch-icon.png, plus
   192px/512px PNGs for Android home-screen icons. All three pages'
   <head> now link to these.

WHAT CHANGED LAST PASS (v1.16)
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

ONE THING NOT FIXED (flagging, not touched)
--------------------------------------------------
partners.html's <title> tag still reads "Referral Partner Program |
[YOUR BUSINESS NAME]" -- a leftover placeholder that was never filled
in with "EmailDone4U". Didn't want to guess and change it without you
confirming that's what should go there -- say the word and I'll fix it
next pass.

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
