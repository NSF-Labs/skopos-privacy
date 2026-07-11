# Skopos — Privacy Policy & Play Data Safety Pack

**Prepared:** 2026-07-11 · For app `com.nsfstudios.skopos` (Skopos 0.3.8+117)
**Publisher:** NSF Studios (legal entity: NSF Labs LLC, Sarasota, FL)

This document contains three things:
1. **Part A** — the privacy policy to publish at a public URL (required before Play will accept your listing).
2. **Part B** — the exact Data Safety form answers, question by question.
3. **Part C** — Aaron's action checklist (what to fill in, where, and the traps).

Everything here is derived from verified facts in the codebase (RE-1/RE-2 audits), not assumptions. **If the app's behavior changes — new endpoint, new permission, analytics added, billing added — this document must be updated before the next release.** A Data Safety form that contradicts app behavior is a policy violation and a takedown risk.

---

# PART A — Privacy Policy

> **Publish this at a public URL before submitting.** Options, easiest first: a GitHub Pages page on the NSF-Labs org (free, permanent, takes ten minutes), a page on an NSF Studios domain if you have one, or a Google Sites page. The URL must be publicly reachable without login, and must stay live for as long as the app is listed.
>
> **Fill in the two placeholders:** `contact@nsflabs.org` and `July 1 2026`.

---

## Privacy Policy for Skopos

**Effective date:** July 1 2026
**Developer:** NSF Studios (NSF Labs LLC), Sarasota, Florida, USA
**Contact:** contact@nsflabs.org

### The short version

Skopos does not have user accounts, does not track you, and contains no analytics or advertising software of any kind. We do not collect, store, or sell your personal information. The app sends your approximate location to public data services so it can tell you what is in the sky above you — that is the only place your data goes, and it is not stored by us.

### What Skopos accesses on your device

**Location.** Skopos uses your device's location to compute what is above you: which aircraft are overhead, where the planets and stars are from your vantage point, local sky conditions, and nearby launch visibility. This is the core function of the app; without it, the app cannot tell you what you are looking at.

**Camera.** Skopos uses your camera only to display the live view behind the augmented-reality sky overlay. **Images and video from your camera are never captured, recorded, saved, transmitted, or shared.** The camera feed exists only on screen, while you are using AR mode.

**Notifications.** If you enable launch alerts, Skopos schedules local notifications on your device to remind you about upcoming rocket launches. These are generated on your device. No notification data leaves your device.

### What leaves your device, and where it goes

To show you live information, Skopos sends requests to public data services. Some of these requests include your approximate coordinates, because a service cannot tell you what is overhead without knowing where "overhead" is.

| Service | What is sent | Why |
|---|---|---|
| adsb.lol | Your approximate coordinates and a search radius | To retrieve aircraft currently flying near you |
| adsbdb.com | An aircraft's identifier or flight callsign (no user data) | To look up the airline, aircraft type, owner, and route of an aircraft you tapped |
| Planespotters.net | An aircraft's identifier (no user data) | To retrieve a photograph of that aircraft |
| Open-Meteo | Your approximate coordinates | To retrieve local sky and cloud conditions |
| National Weather Service (weather.gov) | Your approximate coordinates | To retrieve local weather alerts |
| OpenStreetMap / Carto | Map tile coordinates for the area you are viewing | To draw the map |
| Celestrak | No user data | To retrieve satellite orbital data |
| The Space Devs (Launch Library 2) | No user data | To retrieve rocket launch schedules |
| Open Notify | No user data | To retrieve information about people currently in space |

These services are operated by third parties and have their own privacy practices. Skopos sends only what is necessary to answer the question you asked the app. **We do not attach any identifier to these requests** — no account, no username, no advertising ID, no device fingerprint. The services receive a request for "what is near this point," not "what is near this person."

### What we do NOT do

- We do **not** have user accounts, logins, or profiles.
- We do **not** use any analytics, crash-reporting, telemetry, or advertising software. There is no Firebase, no Crashlytics, no Google Analytics, no Sentry, no ad network, and no third-party tracking SDK in this app.
- We do **not** collect your name, email address, phone number, contacts, photos, files, or browsing activity.
- We do **not** store your location on any server. We do not operate a server that receives your data.
- We do **not** sell, rent, or share your personal information with anyone, for any purpose.
- We do **not** track you across apps or websites.

### Data stored on your device

Skopos stores your settings and preferences (for example, display options and any launch reminders you set) locally on your device. This information stays on your device and is not transmitted to us or anyone else. Uninstalling the app removes it.

### Children

Skopos is not directed at children under 13 and does not knowingly collect personal information from children. Because the app collects no personal information from anyone, it collects none from children.

### Permissions summary

| Permission | Purpose | Optional? |
|---|---|---|
| Location (approximate and precise) | Determine what is in the sky above you | The app's core function requires it; you may decline, but sky and aircraft positioning will not work |
| Camera | Live view behind the AR overlay | Only needed for AR mode; you may decline and use the map views |
| Notifications | Launch reminders you choose to set | Optional |
| Internet | Retrieve live aircraft, sky, weather, and launch data | Required |

### Your choices

You can revoke location, camera, or notification permission at any time in your device's Android settings. Skopos will continue to run with reduced functionality. Uninstalling the app removes all locally stored data.

### Changes to this policy

If we change how Skopos handles data, we will update this policy and update the effective date above. Material changes will also be reflected in the app's Data Safety disclosure on Google Play.

### Contact

Questions about this policy: [CONTACT EMAIL]

---

# PART B — Play Data Safety form: exact answers

> The Data Safety form is a series of questions in Play Console. Answer them exactly as below. **The governing rule: the form must match what the app actually does.** Every answer here is backed by a verified audit finding.

## Section 1 — Data collection and security (overview questions)

| Question | Answer | Why |
|---|---|---|
| Does your app collect or share any of the required user data types? | **Yes** | Location is sent to third-party services. Play counts "transmitted off the device" as collection/sharing, even without a server of your own. |
| Is all of the user data collected by your app encrypted in transit? | **Yes** | All endpoints are HTTPS except one (see the note below) — answer Yes, and read the open-notify note in Part C before submitting. |
| Do you provide a way for users to request that their data is deleted? | **No** (select the option indicating no data is stored / nothing to delete) | Skopos stores no user data on any server; there is nothing to delete. The policy states this. |

## Section 2 — Data types

Declare **exactly** the following. Do not declare anything else.

### ✅ Location → Approximate location

- **Collected:** Yes
- **Shared:** **Yes** ← *(this is the answer people get wrong; coordinates go to adsb.lol, Open-Meteo, and NWS — that is sharing with third parties)*
- **Processed ephemerally?** Yes — it is used to build a request and is not stored
- **Required or optional?** **Required** (core app function)
- **Purposes:** **App functionality** only. *(Do not check Analytics, Advertising, Personalization, or Account management — none apply.)*

### ✅ Location → Precise location

- **Collected:** Yes
- **Shared:** Yes
- **Processed ephemerally?** Yes
- **Required or optional?** Required (core app function)
- **Purposes:** **App functionality** only.

*(Declare both approximate and precise: the app requests both ACCESS_COARSE_LOCATION and ACCESS_FINE_LOCATION.)*

### ❌ Photos and videos — **DO NOT DECLARE**

The camera renders a live preview only. Nothing is captured, stored, or transmitted. Play's Data Safety form covers data **collection**, not permission declarations — a live camera preview that is never captured is not collection. (The camera permission itself is declared in the manifest and is visible to users; that is separate and correct.)

### ❌ Audio — **DO NOT DECLARE**

RECORD_AUDIO was stripped at the manifest merge in RE-2. The app has no microphone access.

### ❌ Everything else — **DO NOT DECLARE**

No personal info, no financial info, no messages, no contacts, no files, no app activity, no web browsing, no device IDs, no crash logs, no diagnostics, no advertising ID. Verified: the codebase contains zero analytics/crash/telemetry SDKs (RE-2 element E9, clean).

## Section 3 — When you add billing (MON-1) — future update

When the $12.95 one-time unlock ships, **you must return to this form** and add:

- **Financial info → Purchase history:** Collected — Yes (Google Play processes the purchase). Shared — No. Purpose: App functionality.
- Google Play Billing handles the payment; Skopos never sees or stores card data. Do **not** declare payment info as collected by your app.
- Update the privacy policy with a short "Purchases" section noting that Google Play processes payment and that Skopos receives only a purchase confirmation.

## Section 4 — Content rating questionnaire

Answer honestly; Skopos is a straightforward utility. Expect **Everyone**. Key answers:

- Violence, sexuality, profanity, drugs, gambling: **No** to all.
- Does the app share the user's location with other users? **No.** *(Sharing coordinates with a data API is not sharing location with other users — this question is about user-to-user exposure.)*
- Does the app contain user-generated content? **No.**
- Does the app have social features / chat? **No.**
- Digital purchases: **Yes**, once MON-1 ships (currently No).

## Section 5 — Other Console declarations

- **Ads:** **No** — Skopos contains no ads. (Declare this; a false "contains ads" flag is as bad as a missing one.)
- **App category:** Suggest **Education** (primary) or **Weather**; "Books & Reference" and "Entertainment" are weaker fits. Education matches the teach-you-the-sky positioning and the audience you want.
- **Target audience:** 13+ (avoids the Families program's extra requirements; the app is not designed for children).
- **Government app / financial features / health:** No to all.

---

# PART C — Aaron's checklist

## Before you can submit

1. **Publish the privacy policy.** Fill in `[CONTACT EMAIL]` and `[EFFECTIVE DATE]` in Part A, publish it at a public URL (GitHub Pages under the NSF-Labs org is the fastest permanent option), and paste that URL into Play Console → App content → Privacy policy.
2. **Pick the contact email carefully.** It becomes **publicly visible on your store listing**. Use a role address you don't mind exposing (e.g. a `support@` or a dedicated Gmail), not your personal address.
3. **Verify the legal-vs-public name split.** Play's legal entity must match your D-U-N-S record (**NSF Labs LLC**); the public developer name shown on the listing can be **NSF Studios**. Set both accordingly.
4. **Create the app as FREE.** Locked by ruling: free download + $12.95 one-time in-app unlock after a 30-day trial. A paid-up-front app can never become free; a free app can always add in-app products. Do not select "Paid."
5. **Enroll in Play App Signing** when prompted at first upload. This makes your upload key resettable if it is ever lost. (Your upload key lives at `~/.keys/skopos/` — backed up to vault and Nextcloud.)
6. **Upload the AAB:** `build/app/outputs/bundle/prodRelease/app-prod-release.aab` (91 MB) → **Internal testing** track → add yourself as a tester.

## One honest flag before you tick "encrypted in transit"

The app makes exactly one plaintext HTTP call: `http://api.open-notify.org/astros.json` (the "people currently in space" feature). RE-2 scoped cleartext to that single host, so nothing else is exposed — but strictly speaking that one request is unencrypted, and it carries **no user data** (it's a static list of astronauts; no coordinates, no identifiers).

Two acceptable paths, your call:

- **Answer "Yes" to encrypted-in-transit** on the basis that no *user data* travels unencrypted (the only unencrypted call contains none). This is defensible and is what most developers would do.
- **Cleanest option (recommended, tiny stage):** check whether `https://api.open-notify.org/astros.json` works — many http-only endpoints have since gained TLS. If it does, switch the URL, delete the network security config exemption, and the question becomes trivially "Yes" with nothing to explain. This is a ten-minute change and would let RE-3 drop cleartext entirely.

## Listing assets you'll need (not blockers for internal testing, required for production)

- **App icon:** 512×512 PNG
- **Feature graphic:** 1024×500 PNG (shown at the top of your listing)
- **Phone screenshots:** minimum 2, up to 8. You already have the best ones — the Delta card with the photo and credit, the AR view with planes labeled in the sky, the map with dead-reckoned traffic, the identity-first card showing a real city pair. Use the ones with airline names and photos; they sell the app in one glance.
- **Short description:** 80 characters max.
- **Full description:** 4,000 characters max.
- *(Drafting these is a separate task — say the word and I'll write them.)*

## Post-upload queue (the polish arc, done in testing)

| Stage | What | Why this order |
|---|---|---|
| **AE-2.3** | Arrival-intent route gate (the SWA4409/one-off miss) | Route honesty is the one thing a paying user could catch you being wrong about |
| **DASH-1** | Animated dashboard hero: day clouds + 737 → night scene + distant launch | Feature-sized, not polish; needs its own diagnosis→build→device pass (ticker on the home screen = battery/thermal considerations) |
| **MON-1** | Play Billing: one-time $12.95 unlock + 30-day trial gate | Gates production, not testing. Verify Billing Library version floor + 15% small-developer fee tier first |
| **H1** | JPL-Horizons / T-ROLL test triage (25 + 5 failures) | Standing release gate: positional accuracy is the app's core promise |
| **RE-3** | Version bump to 1.0.0, production promotion, listing assets live | The finish line |

---

*Generated for Skopos 0.3.8+117 · commit `82c3f11` · all claims traceable to RE-1/RE-2 audit findings*
