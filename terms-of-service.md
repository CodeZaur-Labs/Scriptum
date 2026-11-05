# Terms of Service — Scriptum

**Effective date:** 2026-10-27
**Last updated:** 2026-11-05

---

## 1. Agreement and scope

These Terms of Service ("Terms") govern your use of **Scriptum** — the
Android application, its public APIs (`api-bible.contentfactory.trade`,
`api-bible-users.contentfactory.trade`) and related services (collectively,
the "Service"), operated by CODEZAUR Dominik Lipinski, ("we", "us", the "Operator").

By installing the App, accessing the API, or creating an account, you agree
to these Terms. If you do not agree, do not use the Service.

The Service is offered primarily to consumers. If you use it on behalf of an
organization, you represent that you are authorized to bind that
organization to these Terms.

## 2. What the Service does

The Service provides Bible verses and related functionality, including:

- **Daily verse** — a verse drawn at random from the Bible corpus, shown in
  the App and optionally delivered via a local notification at a time you
  choose. Verse selection is performed per request; a "verse of the day" is
  maintained on your device and is **not** synchronized or identical across
  users or devices.
- **Topics** — an optional, curated set of subject categories (e.g. hope,
  grief, anxiety, family). When selected, verses are drawn from
  pre-computed, relevance-ranked lists for those topics.
- **On-device corpus** — the full text of a Bible edition you select may be
  downloaded to your device (~5–9 MB, varies by edition) for offline
  reading, book browsing, and in-book search.
- **Sharing** — rendering of verse images you may share through other apps.
- **Multiple languages and editions** — currently seven languages, each
  served from a specific Bible translation ("Edition").
- **Reading programs** — curated multi-day reading plans; enrollment and
  progress are tracked on your device.
- **Bookmarks and reading progress** — verses you bookmark or read are
  recorded locally on your device and shown in the App's stats.
- **Accounts** — optional sign-in via email/password or Google Sign-In,
  enabling profile data and activity streaks.

Features marked as planned below may be added, changed, or removed at our
discretion:

- **Premium tier** — a paid subscription unlocking features such as
  **semantic verse search** (free-text queries like "fear of losing my job"
  matched to relevant verses), subject to daily usage quotas.
- **Friends** — optional sharing of activity streaks with contacts added by
  friend code.

## 3. Accounts

### 3.1 Registration

Some features require an account. You may register with an email address
and password or via Google Sign-In. You agree to provide accurate
information and to keep your credentials confidential. You are responsible
for activity performed under your account.

### 3.2 Eligibility

You must be at least **16 years old** (or the age of digital consent in
your jurisdiction) to create an account. The App's reading features may be
used without an account by younger users under parental supervision.

### 3.3 Security and sessions

We issue short-lived access tokens and rotating refresh tokens. We may
revoke sessions, refresh-token families, or entire accounts where we
detect credential theft, token reuse, or other abuse.

### 3.4 Account deletion

You may delete your account at any time from the App's profile screen
(or via the public API). On deletion, your email
address is anonymized and all data linked to the account — OAuth
identities, sessions, activity days, entitlements — is deleted
outright. The account record itself is retained only in anonymized
form, as described in the Privacy Policy.

## 4. Subscriptions and payments

### 4.1 Premium tier

Certain features (including semantic verse search) are or may be offered
under a paid subscription ("Premium"). All purchases are processed by
**Google Play Billing**; we do not collect or store your payment method
details.

### 4.2 Billing terms

- Prices, billing periods, and free-trial terms are shown in the App and
  Google Play at the time of purchase.
- Subscriptions **auto-renew** until cancelled. You can cancel at any time
  in Google Play (Play Store → Profile → Payments & subscriptions); access
  continues until the end of the paid period.
- **Refunds** are governed by Google Play's refund policies. Requests must
  be submitted through Google Play.
- We may change pricing with advance notice as required by the platform;
  changes apply to subsequent billing periods.

### 4.3 Entitlements and quota

Purchase grants an entitlement recorded server-side. Premium features may
be subject to fair-use quotas (e.g. a daily limit on semantic-search
queries). Quotas exist because each query incurs real compute cost; abuse
of quota (automation, circumvention, account sharing) may result in
throttling or suspension. Entitlement status propagates within up to ~15
minutes (access-token lifetime) after purchase, cancellation, or refund.

### 4.4 No purchase guarantee

Premium is an enhancement; the free tier (daily verse, topics, offline
corpus, reading) remains available without payment.

## 5. Content and intellectual property

### 5.1 Biblical texts

The Bible texts served are **public-domain translations** (e.g. King James
Version 1611, Biblia Gdańska 1632, Reina-Valera 1909, Smith & Van Dyke
1865, Synodal Translation 1876, Almeida Livre) with one exception: the
Swahili corpus (Swahili Unlocked Literal Bible, swhulb) is licensed
**CC BY-SA 4.0** — © 2019 Door43 World Missions Community. Where required
by a license, the App displays attribution; do not remove it when
redistributing content under share-alike terms.

### 5.2 Software and materials

The App, APIs, curated topic lists, relevance rankings, artwork, and other
Service materials are owned by the Operator or its licensors and are
protected by intellectual-property law. We grant you a limited,
non-exclusive, non-transferable, revocable license to use the App for
personal, non-commercial purposes.

### 5.3 Your content and shares

Verse images you render and share are generated on your device; you may
share them freely, subject to the underlying text's license (Section 5.1).
We claim no ownership over shares you create.

## 6. Acceptable use

You agree not to:

- violate any law or third-party right;
- scrape, bulk-download, or systematically copy API responses beyond the
  documented corpus-download endpoints;
- bypass or probe authentication, quotas, rate limits, or paid features;
- reverse-engineer token/signing mechanisms or distribute extracted
  credentials (the App's shared API token is a rate-limit barrier, not a
  license to resell access);
- interfere with the Service's infrastructure (excessive load, automated
  credential stuffing, DoS);
- use the Service to generate or distribute misleading, defamatory, or
  harmful material, or to spam others via the sharing features;
- misrepresent the origin of the Service or imply endorsement.

Violation may result in suspension or termination of access and, where
applicable, referral to authorities.

## 7. Disclaimers — please read carefully

### 7.1 Not professional, pastoral, or medical advice

Verse selection is **algorithmic** — random or relevance-ranked by
embedding similarity. It is not pastoral counseling, theological advice,
medical advice, or mental-health treatment. Topics such as *illness*,
*grief*, *anxiety*, or *addiction* do not turn a verse into a substitute
for professional help. **If you are in crisis, contact local emergency
services or a qualified professional.**

### 7.2 Content accuracy and context

- Translations are historical texts that may contain archaic language and
  may reflect the views of their era.
- A single verse presented alone can be ambiguous; the App provides full
  chapter context via the reading features — we encourage reading it.
- Semantic search (when available) matches queries to verses by
  statistical similarity; results may be irrelevant or unexpected. We do
  not guarantee the suitability of any result for your situation.
- The Service does not endorse any denomination, doctrine, or
  interpretation. Inclusion of a translation is a licensing/availability
  decision, not a theological one.

### 7.3 "As is" availability

The Service is provided **"as is" and "as available"**, without warranties
of any kind, express or implied, including merchantability, fitness for a
particular purpose, and non-infringement. The Service is operated as an
independent project on shared infrastructure; we do not guarantee
uninterrupted availability, error-free operation, or preservation of
streaks, bookmarks, or other stored state.

## 8. Privacy

Your use of the Service is also governed by the **Privacy Policy**
(published in the App's Legal section and the Play listing). In short: we
collect the minimum needed to operate — account identifiers, timezone and
locale for streaks/notifications, activity days, and (when subscriptions
ship) billing entitlement records from Google Play. We do not sell your
data.

## 9. Third-party services

The Service relies on third parties with their own terms: Google Play
Billing (payments), Google Sign-In (authentication), and Google embedding
models (semantic-search ranking). We are not responsible for third-party
availability or conduct.

## 10. Changes to the Service and these Terms

We may modify the Service (add/remove features, editions, topics,
languages) and these Terms at any time. For material changes we will
provide notice in the App or by other reasonable means before they take
effect. Continued use after the effective date constitutes acceptance; if
you disagree, stop using the Service and, for paid subscriptions, cancel
before the next renewal.

## 11. Limitation of liability

To the maximum extent permitted by law:

- We are not liable for indirect, incidental, consequential, or punitive
  damages, or for lost profits, data, goodwill, or streaks.
- Our aggregate liability for all claims relating to the Service in any
  12-month period is capped at the greater of **(a) amounts you paid us
  for the Service in that period** or **(b) EUR 25**.
- Nothing in these Terms limits liability that cannot be limited by law
  (e.g. for intent, gross negligence, or mandatory consumer rights in the
  EU, including Poland's consumer-protection provisions).

## 12. Termination

You may stop using the Service and delete your account at any time. We may
suspend or terminate access for breach of these Terms, abuse, security
risk, or legal requirement. On termination: paid entitlements already
granted for the current billing period are honored via Google Play; other
rights granted to you end immediately, except Sections 5, 7, 11, and 13
which survive.

## 13. Governing law and disputes

These Terms are governed by the laws of **Poland**, excluding
conflict-of-law rules. The courts of Warsaw, Poland
have exclusive jurisdiction, **except** that consumers retain the right to
sue in their local courts where mandatory consumer law so provides. EU
consumers may also use the European Commission's online dispute-resolution
platform (where available) or applicable out-of-court complaint bodies.

## 14. Miscellaneous

- If any provision is held unenforceable, the remainder stays in effect.
- Failure to enforce a provision is not a waiver.
- You may not assign these Terms; we may assign them in connection with a
  transfer of the Service, with notice where required.
- These Terms, together with the Privacy Policy, are the entire agreement
  regarding the Service.

## 15. Contact

Questions about these Terms:

- **Email:** codezaur [at] gmail [dot] com
