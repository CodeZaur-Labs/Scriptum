# Privacy Policy — Scriptum

**Effective date:** 2026-10-27
**Last updated:** 2026-11-05

This Privacy Policy explains what data the **Scriptum** app and its
backend services (`api-bible`, `api-bible-users`; collectively the
"Service") collect, why, and what rights you have. It is written to satisfy
the GDPR (the operator is established in Poland) and Google Play's
data-safety requirements.

---

## 1. Data controller

CODEZAUR Dominik Lipinski
Contact: codezaur [at] gmail [dot] com

We are a small independent operation and are not required to appoint a
Data Protection Officer; the contact above reaches the person responsible.

## 2. The short version

- Reading verses **requires no account** and sends no personal data beyond
  what any HTTPS request carries (IP address, request parameters).
- Accounts are optional and collect the minimum: email, timezone,
  display name — plus a password hash for email registration or a Google
  sign-in link for Google accounts.
- **No advertising, no analytics SDKs, no trackers, no cookies, no contact
  upload, no location tracking, no sale of data.** If advertising or
  analytics ever arrive, this policy will be updated and your consent
  collected where required — before anything ships.
- Friends features (when shipped) use **friend codes**, not your address
  book.
- There's almost nothing to export — but we'll send you what we hold on
  request (see §9), and you can delete your account in-app at any time.

## 3. Data on your device

Preferences live **locally** (Android DataStore / app internal storage).
One distinction matters:

**Stored locally and echoed to the API as request parameters:**

- chosen language and topics — sent under the shared app token when you
  are not logged in (the token identifies the app build, not you); when
  you are logged in, the same parameters travel under your account access
  token. The served Bible edition is implied by the language — the app
  does not send a separate `edition` parameter.

**Never leaves your device at all:**

- notification time and enabled flag; notification permission state;
- cached daily verse and fetch date; bookmarks; reading preferences
  (e.g. testament ordering, theme mode);
- your **reading history** — every verse marked as read, with timestamps,
  kept in an on-device database to power progress stats — plus
  reading-program enrollments and completions, and share counts;
- your profile **avatar image** and the cached URL of your Google
  profile photo;
- cached book and topic catalogs;
- the downloaded Bible corpus file (~5–9 MB sqlite, varies by edition)
  and cached artwork.

Daily notifications are scheduled **on-device** (WorkManager); we do not
operate a push-messaging service and never receive a device push token.

## 4. Data we process

### 4.1 Content-API use (anonymous and logged-in)

Requests to `api-bible` carry the parameters you chose (language, topics;
API clients may also send an `edition` key). Anonymous use is authorized
by a shared app token that identifies the app build, not you. When you are
logged in, requests carry your account access token instead, so they are
technically linkable to your account — we do not use this to profile your
reading. Our infrastructure necessarily processes:

| Data | Purpose |
|---|---|
| IP address | serving responses; Cloudflare rate limiting and abuse protection |
| Request parameters (lang, topics, optional edition), timestamps | serving content; aggregate reliability monitoring |

We do **not** build per-device or per-account profiles from this data.

### 4.2 Account data (if you register)

| Data | Source | Purpose |
|---|---|---|
| Email address | you | login, account identification |
| Password | you | stored **only** as a one-way cryptographic hash (argon2id) — never plaintext |
| Display name | you (optional) | profile display |
| Timezone; locale (optional) | you / device | streak day boundaries, localization |
| Google account `sub` and email | Google Sign-In | OAuth login link (ID token verified against Google's keys; we never see your Google password) |
| Device label (e.g. "Pixel 8") | your device | session list / audit of refresh tokens |
| Refresh tokens | issued by us | stored **only** as SHA-256 hashes; rotate on every use |

Profile photos are picked and stored **on your device only** — they are
never uploaded to us. If you sign in with Google, the app may fetch your
public Google profile image directly from Google to display it locally.

### 4.3 Activity and streaks

- `activity_days`: the calendar dates (in **your** timezone) on which the
  app reported an open — used solely to compute and display streaks.

### 4.4 Purchases and entitlements (when shipped)

- `entitlements`: your plan key, status, expiry, source
  (`play_billing`), and the Play purchase token — used to verify and
  honor your subscription via the Google Play Developer API.
- We **never** see or store payment card details; billing is entirely
  inside Google Play.

### 4.5 Paid-feature usage (semantic verse search — when shipped)

- Your **free-text query** is sent to our AI embedding provider
  (currently Google) solely to compute a relevance ranking, and to you
  we return only verse results. The query is used for that single
  request and **is not stored** — not as plaintext, not as a hash;
  there is no server-side history of what you searched.
- A **daily usage quota** is enforced per account server-side; the
  counter is transient and is not persisted as a per-event ledger.
- Treat queries as potentially sensitive: do not enter information you
  would not send to a third-party AI service.

### 4.6 Technical logs

Standard web logs (nginx/Cloudflare: IP, path, status, timestamp) kept for
security and debugging. Access and refresh tokens are never logged.

## 5. Legal bases (GDPR)

| Processing | Basis |
|---|---|
| Serving verses, corpus downloads | Legitimate interest (Art. 6(1)(f)) — running a public content API |
| Account creation, login, tokens | Contract (Art. 6(1)(b)) |
| Streaks, activity days | Contract (Art. 6(1)(b)) — the feature you enabled |
| Subscription verification, purchase audit (when shipped) | Contract + legal obligation (Art. 6(1)(b), (c)) — consumer/accounting law |
| Security logs, rate limiting, abuse prevention | Legitimate interest (Art. 6(1)(f)) |
| Semantic-search queries to the embedding provider (when shipped) | Contract (Art. 6(1)(b)) — the feature you invoked |

*(b) = needed to provide the feature you asked for; (c) = the law
requires it (consumer/accounting rules); (f) = our justified operational
interest — you may object to (f) (see §9).*

## 6. Who we share data with (processors)

| Third party | Role | What they receive |
|---|---|---|
| Google (Sign-In, Play Billing; currently also the embedding API) | auth, payments, search ranking | Google ID tokens (verified server-side); purchase tokens; your search query text |
| Cloudflare | CDN/WAF, TLS termination, rate limiting | all public-API traffic metadata (IP, request line) |
| Hetzner | hosting (VPS in the EU) | the whole database and logs — as our hosting sub-processor |

No data is sold, rented, or shared for advertising. There are no other
recipients today; any future processor will be listed here before it
receives data.

## 7. International transfers

Google and Cloudflare process data globally, including in the United
States, under their own data-processing terms incorporating EU Standard
Contractual Clauses (or equivalent mechanisms under GDPR Art. 46). Hosting
and our database remain in the EU.

## 8. Retention

| Data | Retention |
|---|---|
| Account record (email, name, tz, locale) | until you delete the account |
| Refresh-token hashes | each token is valid max 30 days; rotated on every use, revoked on logout or password change; **deleted** with the account |
| Activity days | **deleted** with the account |
| Entitlements | **deleted** with the account — Google Play retains the underlying purchase record independently (when subscriptions ship) |
| Server logs (IP) | ~30 days |
| Deleted accounts | the account record is kept only in anonymized form (the email is rewritten to a generated placeholder); **all** data linked to it — OAuth identities, refresh tokens, activity days, entitlements — is deleted |

Deleting the app without an account deletes all local data with it — there
is nothing else to remove.

## 9. Your rights

As an EU/EEA user you may:

- **access** your data (in-app profile);
- **rectify** it (in-app profile editing);
- **erase** your account (in-app "Delete account", or via the public API) —
  anonymized as described above;
- **restrict or object** to processing, including legitimate-interest
  processing;
- **port** your data (contact us — we'll export the records we hold);
- **withdraw consent** where processing is consent-based (e.g. stop using
  Google Sign-In) without affecting prior processing;
- **lodge a complaint** with the Polish supervisory authority — Prezes
  Urzędu Ochrony Danych Osobowych (UODO), uodo.gov.pl — or your local DPA.

We make **no automated decisions** about you and do not build profiles
(GDPR Art. 22).

To exercise any right, email codezaur [at] gmail [dot] com. We respond within one
month.

## 10. Security measures

- TLS everywhere (Cloudflare, strict mode); no plaintext traffic.
- Passwords hashed with **argon2id**; refresh tokens stored only as
  SHA-256 hashes; access JWTs are short-lived (15 min) Ed25519 tokens —
  the signing private key exists only on the accounts service.
- Refresh-token rotation with reuse detection: a replayed token revokes
  the whole session family.
- Rate limiting at the edge; auth endpoints have uniform error responses
  to limit account enumeration.
- Backend isolation: the public content edge holds no user data and no
  account credentials — the only secrets it needs are the shared app
  token (a rate-limit barrier distributed with the app, not a user
  credential) and a scoped embedding-API key for the search feature;
  the accounts service reaches only the user database.

No system is perfectly secure; if a breach affects your data, we will
notify you and the supervisory authority as required by GDPR Art. 33–34.

## 11. Children

Accounts require age **16+** (or your jurisdiction's digital-consent age).
Anonymous reading features collect no personal data and may be used by
younger users under parental supervision. We do not knowingly collect
children's personal data; contact us to remove any such account.

## 12. Changes

We may update this policy; material changes are announced in-app before
taking effect. The "last updated" date always reflects the current
version. Continued use after the effective date means acceptance.

## 13. Contact

Privacy questions, data requests, complaints:

- **Email:** codezaur [at] gmail [dot] com
