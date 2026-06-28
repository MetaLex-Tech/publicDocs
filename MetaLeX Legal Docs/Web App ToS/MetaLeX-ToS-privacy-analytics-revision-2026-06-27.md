# MetaLeX Web App ToS — Privacy & Analytics Revision

> **Status:** DRAFT for legal review · **Prepared:** 2026-06-27
> **Base document:** `MetaLeX-ToS-1.22.25.pdf` (Date of Initial Publication 1/22/2025)
> **Proposed new version:** "Last Updated: 6/27/2026" (date to be set by counsel on publication)
>
> This document is a **drafting aid prepared by Claude**, not legal advice, and must be reviewed
> by MetaLeX counsel before publication. It revises the ToS privacy provisions to disclose a
> **"max-aggressive" deployment of the analytics provider** — assumed to mean PostHog configured
> with: product analytics (pageviews + custom events), DOM **autocapture**, **session replay /
> recordings**, **heatmaps**, web-vitals/performance capture, **feature flags / A-B experiments**,
> **surveys**, **wallet-based person identification**, IP-based geolocation, persistent
> **cookies / local storage**, cross-session and cross-device **profiling**, optional
> **data-warehouse enrichment** (joining third-party data sources via the provider's
> data-warehouse feature), hosted in the **United States** with extended retention.
>
> Note: the analytics integration as currently built in the webapp is deliberately *narrower*
> than this (no autocapture, no session replay, `identified_only` profiles). This revision is
> drafted to the **max-aggressive** envelope you asked to assume, so the ToS would cover the
> full feature set even if it is switched on later. Trim to match actual configuration if you
> prefer the disclosures to track what is actually enabled.

---

## 1. Assessment of the current ToS privacy posture

| # | Current state | Location |
|---|---|---|
| 1 | The **only** privacy clause is §3.3 "Privacy Policy" — a single sentence: the Site Operator "may directly or indirectly collect and temporarily store personally identifiable information for operational purposes, including for the purpose of identifying blockchain addresses or IP addresses" that may indicate prohibited use, and "will have no obligation of confidentiality" except as required by law. | §3.3 |
| 2 | A list of data points used for **access control / geofencing** (identity, blockchain address, IP address, ISP, VPN provider, metadata, browser software, device type, wallet application, wallet device, region of citizenship/residence, current location). This is a data-collection disclosure in substance but framed only as grounds for denial of access. | §2.6 |
| 3 | A reservation of the right to **cooperate with investigations and disclose information**. | §2.7 |
| 4 | A Prohibited-Use reference requiring compliance with "any other terms of service, **privacy policy**, trading policy or other contract governing the use of the Site" — **but no privacy policy exists** in the repo or (apparently) on the Site. | §4.2 |
| 5 | Age: the Summary says users must be "at least thirteen years of age," while §5.1 requires "older than eighteen years of age." This **internal inconsistency** is a problem once profiling/analytics of minors is in scope. | Summary; §5.1 |

### Gaps relative to max-aggressive analytics

The current ToS does **not** disclose, and would need to, any of the following:

1. **Use of a third-party analytics processor** (PostHog) and any sub-processors.
2. **Categories of data collected via analytics** beyond compliance screening — event/usage data, device & connection data, autocaptured interactions, **session recordings of on-screen activity**, survey responses, and inferred/derived data (cohorts, funnels, experiment assignments, profiles).
3. **Session replay specifically** — recording of a user's interactions with the Site (clicks, navigation, inputs, page content). This is high-sensitivity and needs express notice plus a masking representation.
4. **Cookies / local storage and similar tracking technologies** (PostHog sets a persistent distinct-id and session identifiers). Implicates ePrivacy / cookie-consent regimes in the EEA and UK.
5. **Persistent, cross-session and cross-device tracking and profiling**, including identification keyed to the user's **wallet address**.
6. **Purposes** beyond sanctions/compliance — product analytics, product improvement, experimentation (feature flags / A-B testing), debugging via session replay, surveys, and measurement.
7. **International data transfer** — PostHog US Cloud means data on EEA/UK/Swiss users is transferred to the United States; needs an SCC / UK IDTA / transfer-mechanism statement.
8. **Data retention** — the current word "**temporarily**" is no longer accurate where analytics data may be retained for extended periods; a retention statement is required. (Confirm the actual retention period configured with the Analytics Provider.)
9. **Data-subject / consumer rights** and how to exercise them (access, deletion, objection, opt-out), plus a privacy contact.
10. **Legal bases (GDPR/UK GDPR)** — legitimate interests for analytics/security, **consent** for non-essential cookies and session replay where required, legal obligation for compliance screening.
11. **CCPA/CPRA** — cross-context behavioral analytics can constitute a "**share**" (and potentially a "sale"); requires notice at collection, an opt-out, and honoring the **Global Privacy Control**.
12. The blanket "**no obligation of confidentiality**" in §3.3 is inconsistent with operating behavioral analytics on identifiable data and with mandatory data-protection obligations; it should be qualified.
13. The **13-vs-18 age inconsistency** (item 5 above) should be resolved to 18+, with a no-children's-data representation, given profiling.
14. The dangling reference to a "**privacy policy**" in §4.2 should resolve to a real instrument — either a standalone Privacy Notice or the expanded §3.3 + new Exhibit B below.

---

## 2. Drafting approach

Because there is no standalone Privacy Policy, this revision keeps everything inside the ToS:

- a new **Summary** bullet (notice at a glance);
- new **defined terms** in §1;
- a **replacement §3.3** that states the substance and incorporates the detail by reference;
- a conforming tweak to **§4.2**; and
- a new **Exhibit B (Privacy Notice)** carrying the granular disclosures, including regional (GDPR/UK and California) addenda and a cookies/SDK table.

Provider is referenced through a flexible defined term (**Analytics Provider**, "currently PostHog") plus a pointer to a maintained sub-processor list, so the document does not break if the provider or feature mix changes.

---

## 3. Proposed changes (redline)

### 3.1 New Summary bullet (add to "SUMMARY OF TERMS")

Add after the existing data/research bullets:

> ● acknowledge and, where required, consent that the Site uses **first-party and third-party analytics, cookies and similar technologies, and may record your interactions with the Site (including session replays)**, may associate that activity with your **blockchain/wallet address and device**, and may transfer this data to service providers (including in the **United States**) for analytics, security, product improvement, experimentation and compliance, all as described in **Section 3.3** and **Exhibit B (Privacy Notice)**;

### 3.2 New defined terms (add to §1 "Certain Defined Terms")

> ● "***Analytics Provider***" means each third-party analytics, product-experience, session-replay, feature-flagging or survey service the Site Operator uses to collect and process Usage Data and other Personal Data in connection with the Site, currently including PostHog and any successor or additional provider used by the Site Operator from time to time.
>
> ● "***Cookies***" means cookies, local storage, software development kits (SDKs), pixels, tags, device identifiers and other similar tracking technologies.
>
> ● "***Personal Data***" means information that identifies, relates to, or could reasonably be linked with an identified or identifiable natural person or household, including a blockchain or wallet address to the extent it is linked or linkable to such a person.
>
> ● "***Process***" (and "Processing") means any operation performed on Personal Data, including collection, recording, organization, storage, use, analysis, disclosure, transfer and deletion.
>
> ● "***Session Recordings***" means recordings or reconstructions of a User's interactions with the Site, which may include page views, navigation, mouse movements, clicks, taps, scrolling, keystroke timing and the content of pages viewed (excluding fields masked by the Site Operator or the Analytics Provider).
>
> ● "***Sub-Processor***" means a third party engaged by the Site Operator or an Analytics Provider to Process Personal Data in connection with the Site.
>
> ● "***Usage Data***" means data about how Users access and use the Site, including pages and screens viewed, the sequence and timing of interactions, features used, events such as connecting a wallet or initiating a draft transaction, autocaptured interactions with Site elements, device and connection information (such as IP address, approximate location derived from IP address, browser, operating system, device type, language and referring URL), and inferred or derived data such as cohorts, funnels and experiment assignments.

### 3.3 Replacement for §3.3 ("Privacy Policy" → "Privacy; Analytics; Cookies")

**DELETE the current §3.3 in full** and replace with:

> **3.3 Privacy; Analytics; Cookies**
>
> (a) **Collection and use.** The Site Operator and its Analytics Providers and Sub-Processors collect, generate and Process Personal Data and Usage Data in connection with the Site, including (i) blockchain and wallet addresses and other onchain identifiers; (ii) device and connection data, including IP address and approximate location derived from it; (iii) Usage Data, including autocaptured interactions with Site elements; (iv) Session Recordings; (v) responses to any surveys presented on the Site; and (vi) data inferred or derived from the foregoing, including profiles, cohorts and experiment assignments. The Site Operator Processes this data to operate, secure, debug and improve the Site; to measure and analyze usage; to run product experiments (including feature flags and A-B tests); to present and analyze surveys; to identify and prevent Prohibited Uses and use from prohibited jurisdictions or by sanctioned persons; and to comply with applicable law. The Site Operator may associate Usage Data and Session Recordings with a User's blockchain or wallet address and device and may link activity across sessions and devices.
>
> (b) **Cookies and similar technologies.** The Site and its Analytics Providers use Cookies, including persistent identifiers used to recognize a User and a User's device across sessions. To the extent applicable law requires consent for non-essential Cookies or for Session Recordings, or requires the Site Operator to honor an opt-out preference signal (such as the Global Privacy Control), the Site Operator's policy is to comply with such requirements. Users may also control Cookies through their browser settings as described in Exhibit B.
>
> (c) **Service providers; international transfer.** The Site Operator discloses Personal Data and Usage Data to its Analytics Providers and Sub-Processors, which Process such data on the Site Operator's behalf. The Analytics Provider currently hosts data in the **United States**, and use of the Site may therefore involve the transfer of Personal Data to, and Processing in, the United States and other jurisdictions whose data-protection laws may differ from, and may provide less protection than, those of the User's jurisdiction. By using the Site, each User acknowledges and, to the extent permitted by applicable law, consents to such transfer and Processing. The Site Operator does not represent that any particular cross-border transfer mechanism is currently in place; to the extent applicable law requires a transfer mechanism for such transfers, the Site Operator's policy is to seek to implement and rely on a mechanism recognized under applicable law. Users may request information about the Analytics Providers and Sub-Processors used by the Site Operator at legal@metalex.tech.
>
> (d) **Retention.** The Site Operator and its Analytics Providers retain Personal Data and Usage Data for as long as necessary for the purposes described in this Section 3.3 and Exhibit B, which may be up to several years, and thereafter delete or de-identify such data except where longer retention is required or permitted by applicable law.
>
> (e) **Confidentiality.** Except (i) as required by applicable law (including applicable data-protection law), (ii) as described in this Section 3.3 and Exhibit B, or (iii) as set forth in a separate written agreement with a User, the Site Operator does not undertake any obligation of confidentiality with respect to information collected by the Site, and may disclose such information as described in Section 2.7 and Exhibit B.
>
> (f) **Your choices and rights; further detail.** Additional detail regarding the Personal Data the Site Operator Processes, the purposes and legal bases for Processing, recipients, international transfers, retention, the Cookies used, and the rights available to Users (including, as applicable, rights of access, correction, deletion, objection, restriction, portability, and to opt out of "sales" or "sharing" of Personal Data and of cross-context behavioral analytics) and how to exercise them, is set forth in **Exhibit B (Privacy Notice)**, which is incorporated into and forms part of these Terms. To exercise a right or ask a privacy question, contact legal@metalex.tech. In the event of a conflict between this Section 3.3 and Exhibit B, Exhibit B controls as to the subject matter it addresses.

### 3.4 Conforming change to §4.2

In the Prohibited-Use bullet that currently reads "...any other terms of service, privacy policy, trading policy or other contract governing the use of the Site," change "privacy policy" to:

> "...the privacy terms set forth in Section 3.3 and Exhibit B..."

so the reference resolves to an instrument that actually exists.

### 3.5 Age conforming change (recommended)

Resolve the 13-vs-18 inconsistency by amending the first Summary bullet from "at least thirteen years of age" to "**at least eighteen years of age (or the age of majority in your jurisdiction, if higher)**," consistent with §5.1, and add to §5 a representation that the User is not under 18 and is not providing the Personal Data of any person under 18. (Strictly an age/eligibility fix, but it is load-relevant to the privacy posture once profiling is enabled.)

---

## 4. New Exhibit B — Privacy Notice (full drop-in text)

> ## EXHIBIT B
> ## PRIVACY NOTICE
>
> *Last Updated: 6/27/2026.* This Privacy Notice forms part of the Terms and describes how MetaLeX Labs, Inc. (the "Site Operator," "we," "us") Processes Personal Data in connection with the Site. Capitalized terms used but not defined in this Exhibit B have the meanings given in the Terms.
>
> **1. Who is responsible.** The Site Operator is the controller of Personal Data Processed in connection with the Site. Contact: legal@metalex.tech.
>
> **2. Categories of Personal Data we Process.**
> - **Onchain identifiers:** blockchain and wallet addresses, transaction-related identifiers, and activity you initiate through the Site.
> - **Device and connection data:** IP address, approximate location derived from IP address, browser type and version, operating system, device type, screen size, language and referring or exit URLs and campaign parameters.
> - **Usage Data:** pages and screens viewed; the sequence, timing and duration of interactions; features used; and events such as connecting a wallet, initiating a draft transaction, tokenizing a position, minting a certificate, or signing an agreement.
> - **Autocaptured interactions:** clicks, taps, form-field interactions and similar interface events, excluding the contents of fields masked by us or the Analytics Provider.
> - **Session Recordings:** recordings or reconstructions of your interactions with the Site as described in the Terms. Where Session Recordings are enabled, we intend to configure the Analytics Provider to mask password, secret and other sensitive input fields; however, masking may be incomplete or unavailable, and you should not enter Personal Data into any field that you do not wish to be recorded.
> - **Survey responses:** information you provide in response to surveys presented on the Site.
> - **Inferred and derived data:** cohorts, funnels, profiles, experiment and feature-flag assignments and similar analytics outputs.
> - **Compliance data:** information used to detect and prevent Prohibited Uses, sanctioned-person use and use from prohibited jurisdictions.
>
> **3. Sources.** We collect this data (a) directly from your device and browser when you use the Site; (b) from the Analytics Provider and other Sub-Processors; and (c) from your connected wallet and public blockchains.
>
> **4. Purposes.** We Process this data to: operate, secure, maintain and debug the Site; measure and analyze usage and performance; improve the Site and develop new features; run product experiments (feature flags and A-B tests); present and analyze surveys; recognize you across sessions and devices; detect, prevent and investigate Prohibited Uses, fraud and security incidents; screen for sanctioned persons and prohibited jurisdictions; and comply with law and respond to lawful requests.
>
> **5. Cookies and similar technologies.** The Site and the Analytics Provider use Cookies, including a persistent analytics identifier and session identifiers stored in your browser, to recognize you and your device, maintain analytics continuity, run experiments and (if enabled) capture Session Recordings. Some Cookies are strictly necessary to provide the Site; others are analytics or functional Cookies. To the extent applicable law requires consent for non-essential Cookies, our policy is to use them only as permitted by that law. You can control Cookies through your browser settings and, where offered, through any consent controls made available on the Site; disabling some Cookies may affect Site functionality.
>
> **6. Analytics Provider; Sub-Processors; recipients.** We use the Analytics Provider (currently PostHog) to Process Personal Data on our behalf. We may also disclose Personal Data to: other Sub-Processors and service providers (such as hosting, infrastructure and, if enabled, data-warehouse and other data sources that we may connect for analytics, if any); professional advisors; acquirers in a corporate transaction; and governmental, regulatory or law-enforcement authorities as described in Section 2.7 of the Terms or as required by law. You may request information about the Analytics Providers and Sub-Processors we use at legal@metalex.tech.
>
> **7. International transfers.** We and our Sub-Processors may Process Personal Data in the **United States** and other countries whose laws may not provide the same level of protection as your home jurisdiction. By using the Site you acknowledge and, to the extent permitted by applicable law, consent to this transfer and Processing. We do not represent that any particular cross-border transfer mechanism is currently in place. To the extent applicable law requires a transfer mechanism (such as the European Commission's Standard Contractual Clauses or the UK International Data Transfer Addendum) for such transfers, our policy is to seek to implement and rely on a mechanism recognized under applicable law. You may contact us at legal@metalex.tech with questions about cross-border transfers.
>
> **8. Retention.** We retain Personal Data for as long as necessary for the purposes described above, which may be up to several years for analytics data, and shorter periods for Session Recordings as configured from time to time. We retain compliance data for as long as necessary to meet legal and security obligations. We then delete or de-identify the data, except where longer retention is required or permitted by law.
>
> **9. Security.** We seek to use technical and organizational measures we consider reasonable to protect Personal Data. No method of transmission or storage is completely secure, and we do not warrant or guarantee the security of Personal Data; use of the Site is at your own risk as further described in the Terms.
>
> **10. Your rights.**
> - **EEA / UK / Switzerland.** Subject to applicable law, you have the rights to access, rectify, erase, restrict and port your Personal Data, to object to Processing (including Processing based on legitimate interests and any direct-marketing analytics), and to withdraw consent at any time without affecting prior Processing. Our legal bases are: our **legitimate interests** in operating, securing, measuring and improving the Site (Art. 6(1)(f) GDPR); your **consent** for non-essential Cookies and Session Recordings where required (Art. 6(1)(a)); **compliance with a legal obligation** for sanctions and regulatory screening (Art. 6(1)(c)); and **performance of a contract** where Processing is necessary to provide the Site (Art. 6(1)(b)). You may lodge a complaint with your supervisory authority.
> - **California (CCPA/CPRA).** We collect the categories of Personal Information described in Section 2 above for the purposes in Section 4. Our use of cross-context behavioral analytics and third-party analytics Cookies may constitute "**sharing**" (and, depending on configuration, a "**sale**") of Personal Information under California law. Subject to applicable law, you have the right to know, to delete, to correct, and to **opt out of the sale or sharing** of your Personal Information. To the extent applicable law requires us to honor the **Global Privacy Control** or another opt-out preference signal, our policy is to do so. We do not knowingly sell or share the Personal Information of consumers we know to be under 16. We will not discriminate against you for exercising your rights.
> - **How to exercise.** Submit requests to legal@metalex.tech, use the Analytics Provider's opt-out where available, or set an opt-out preference signal in your browser. We will verify and respond to requests as required by applicable law. Because the Site is provided to sophisticated users on an as-is basis and we may have limited ability to associate analytics identifiers with a verified individual, some requests may require additional information to fulfill.
>
> **11. Children.** The Site is not directed to, and may not be used by, anyone under 18. We do not knowingly Process the Personal Data of anyone under 18. If you believe a minor has provided Personal Data, contact legal@metalex.tech.
>
> **12. Changes.** We may update this Privacy Notice from time to time as described in Section 8.5 of the Terms. The "Last Updated" date indicates when it was last revised.

---

## 5. Open questions for counsel

1. **Match disclosures to actual configuration?** As built, the webapp uses analytics-only with autocapture **off**, session replay **off**, and `identified_only` profiles. This draft covers the max-aggressive envelope. Decide whether to (a) publish the broad version now (future-proof) or (b) trim session-replay/autocapture/cookie-consent language to current reality and re-broaden when features are enabled.
2. **Standalone Privacy Policy vs. in-ToS Exhibit B.** §4.2 references a "privacy policy." This draft satisfies that by adding Exhibit B; alternatively, publish a standalone Privacy Policy and cross-reference it. A standalone notice is easier to update without re-versioning the whole ToS.
3. **Consent UX.** EEA/UK cookie-consent and session-replay consent generally require a consent banner/manager. The current Site has none. If max-aggressive analytics goes live for EEA/UK users, a consent mechanism is likely needed; the ToS language alone is not sufficient for ePrivacy consent.
4. **Data region.** Confirm US vs EU PostHog region. If EU users are material, an EU-region deployment reduces transfer exposure and may simplify the §3.3(c)/Exhibit B §7 language.
5. **Sub-processor list.** Decide whether to publish a maintained sub-processor page (recommended) and link it, rather than "available on request."
6. **"Sale/share" position (California).** Confirm whether you want to characterize third-party analytics as a "share" and stand up a "Do Not Sell or Share" link + GPC honoring, or configure analytics to avoid that characterization.
7. **Wallet address as Personal Data.** This draft treats a wallet address as Personal Data when linkable to an individual (the prudent position). Confirm this is the intended posture.
8. **Version mechanics.** New "Last Updated" date and filename (e.g., `MetaLeX-ToS-6.27.26.pdf`). The canonical published PDF should be generated from your source document with these edits applied, not reconstructed from text extraction (to preserve formatting fidelity).
9. **No representations of practices not yet in place (important).** This draft deliberately does **not** assert as current fact any protective practice that may not actually be implemented. Specifically, the following were written as obligations-to-comply or disclosures rather than affirmative representations: (a) cross-border transfer mechanisms (SCCs / UK IDTA) — stated as "we do not represent that any particular mechanism is currently in place; to the extent law requires one, our policy is to seek to implement it," not "transfers are made pursuant to SCCs"; (b) cookie/session-replay **consent tooling** (no consent banner exists today); (c) **honoring the Global Privacy Control / opt-out signals**; (d) **input masking** in Session Recordings ("intend to," not "we mask"); (e) a **maintained sub-processor list** ("you may request information," not "a current list is available"); (f) the **CCPA 12-month collection lookback** (changed to present-tense "we collect"); and (g) **security measures** (softened to "we seek to use measures we consider reasonable," with an express no-warranty). **Once a given practice is actually implemented** (e.g., SCCs executed with PostHog, a consent manager deployed, GPC honored, masking configured, a sub-processor page published), counsel can and should restore the firmer affirmative language for that item.
