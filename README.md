# Borizago — Book. Ride. Explore.

An installable shuttle-booking web app for **Boriza Shuttle & Tours** in Namibia.

A Digital Experience by [SolarSpin Technologies](https://freeman-ipumbu.pages.dev/).

[**Open the live app →**](https://borizashuttles.pages.dev/)

![Borizago desktop booking experience](assets/borizago-desktop-2026.png)

<p align="center">
  <img src="assets/borizago-mobile.jpg" width="390" alt="Borizago mobile booking experience">
</p>

## The product

Borizago turns a WhatsApp-led booking process into a fast, guided journey that works in a browser and installs directly to a phone home screen. Customers can travel between Windhoek, Okahandja, Karibib, Usakos, Arandis, Swakopmund and Walvis Bay without downloading an app-store package.

The responsive website and installed progressive web app share one Cloudflare-hosted booking system, so seat counts, fares, schedules and payment state stay consistent everywhere.

On phones, the header keeps the Borizago wordmark and a compact **Request service** action visible without crowding the viewport, while the persistent bottom navigation provides direct access to shuttles, services, journeys and help.

## Brand refinement

The visual update improves Boriza’s existing identity instead of replacing it. The navy-and-white shuttle badge, route arcs and **BST** initials remain recognisable, while a new full-bleed square app icon stays legible in browser tabs, home-screen tiles, dashboard notifications and the compact mobile header. The fuller heritage badge remains the public-facing artwork on the booking page.

The home page also includes a reusable 9:16 **Boriza status pack** for WhatsApp and Facebook: a daily shuttle reminder, a seats-available post and a services overview. Each graphic can be opened or downloaded at full resolution. These are marketing templates only; schedules, availability and prices still come from the live system and staff-controlled records.

## Customer journey

1. Choose the departure town, destination and date.
2. Select a published trip with live seat availability and passenger fares.
3. Add named Adult, Pensioner, Student and Child passengers.
4. Choose Boriza's operational pickup/drop-off zones, then enter the exact street, erf, building, gate or landmark for both ends.
5. Use a deliberate Namibia-only address search for precise street/place suggestions, or add a one-tap GPS pin. The written description remains required and editable.
6. Provide a primary mobile number plus a named alternative/emergency contact with a different required 10-digit number.
7. Review the route, passengers, both exact locations, map links, server-calculated total and cancellation policy.
8. Confirm the details and actively accept the Terms & Conditions, including luggage, safety and no-refund safeguards.
9. Choose EFT or office payment, confirm the booking and receive a unique reference.
10. Share the confirmation through WhatsApp and revisit it under **My journeys**.

Customers can also request tours, airport transfers, private transfers and parcel transport. Those forms use the same hardened address/map and two-contact onboarding, then capture the luggage, flight or recipient details Boriza needs for a personal quote.

![Borizago service request experience](assets/borizago-services-2026.png)

The installed app detects standalone mode and removes its own install prompt. The booking flow uses a private first-party customer identifier, with no dependency on ChatGPT authentication or hosting.

## Support and travel resources

The public [Help & FAQ](https://borizashuttles.pages.dev/help) explains booking, payment, changes, service requests and pickup/drop-off points in plain language. WhatsApp help is available throughout the journey at **+264 85 772 4329**, with **+264 81 731 4947** available for calls. The footer and home support panel also connect customers to [Boriza on Facebook](https://www.facebook.com/share/14qinXBbi7H/).

Customers can keep the [payment notice](https://borizashuttles.pages.dev/payment-notice.jpeg), [bus-rules poster](https://borizashuttles.pages.dev/bus-rules.jpeg), [daily shuttle fare guide](https://borizashuttles.pages.dev/boriza-daily-shuttle-fares.jpeg), [parcel policy](https://borizashuttles.pages.dev/boriza-parcel-policy.jpeg), [Hosea Kutako–Windhoek transfer guide](https://borizashuttles.pages.dev/boriza-airport-windhoek-transfer.jpeg) and [Hosea Kutako–coast transfer guide](https://borizashuttles.pages.dev/boriza-airport-coast-transfer.jpeg) on their phone. Every poster opens at its natural proportions and can be downloaded directly. The booking flow explains EFT, wallet proof-of-payment and office payment, while the safety and parcel notices cover the practical onboard, luggage, cutoff and restricted-item guidance.

The airport request screen presents the advertised N$400 per-person or N$2,000 group Windhoek transfer and the N$7,000 group coast transfer, with Boriza confirming final availability, pickup area and price. The parcel screen presents the 08:00–11:00 same-day cutoff, next-day handling after the cutoff, expected arrival window and starting rates. The daily shuttle poster is clearly treated as an advertised fare guide; admin-managed trips remain the source of truth for live departure times, capacity and bookable fares.

The review screen requires two deliberate confirmations before submission: the customer verifies the passenger, contact and pickup details, then accepts the Terms & Conditions. The acceptance timestamp and terms version are recorded with the booking. The terms explain that customer cancellations are non-refundable because a released seat may remain vacant, subject to rights that cannot lawfully be excluded; if Boriza cancels or cannot provide the trip, the available remedy is handled according to the terms and applicable law. They also cover the supplied allowance of two medium bags or one big bag per passenger, extra luggage charges, valuables, prohibited items, pickup timing and passenger conduct.

## Timetable and route model

The public timetable reflects Boriza’s supplied operating times:

- Morning: Windhoek 05:30 → Okahandja 07:30 → Karibib 09:00 → Usakos 09:30 → Arandis 10:30 → Swakopmund 11:00 → Walvis Bay 12:30.
- Afternoon: Walvis Bay 13:00 → Swakopmund 14:00 → Arandis 15:00 → Usakos 16:00 → Karibib 16:45 → Okahandja 18:00 → Windhoek 19:30.

The route engine expands these corridors into 42 valid town-to-town combinations while preventing reverse or identical-location selections. Every segment uses the same underlying vehicle record, so a seat booked from an intermediate stop still reduces the shared vehicle capacity.

The confirmed per-person matrix is directional. Windhoek to Okahandja is N$150, while Windhoek to Karibib or Usakos is N$270. Karibib or Usakos to Swakopmund or Walvis Bay is N$270; Arandis to either coastal town is N$150. Walvis Bay, Swakopmund or Arandis to Okahandja is N$300. Usakos or Karibib to Okahandja or Windhoek is N$270, and Walvis Bay, Swakopmund or Arandis to Usakos or Karibib is N$270. Walvis Bay to Windhoek remains N$300, while Walvis Bay to Swakopmund or Arandis remains N$150. The booking API owns this matrix and recalculates the total before reserving a seat. The corresponding Walvis Bay drop-off points are Swakopmund; Arandis service station; Shell Service Station in Usakos; Agra Service Station in Karibib; Wumpi Service Station / Shell Service Station in Okahandja; and home drop-off in Windhoek.

## Operations dashboard

Boriza staff use a private, signed server session to manage the service. The dashboard can:

- create and edit routes and trips;
- change departure times, pickup points, vehicles, capacity and passenger fares;
- publish or hold trips;
- search bookings and customers;
- edit, confirm or cancel bookings;
- mark payments pending or paid;
- inspect passenger manifests and remaining seats.
- view both required phone numbers, exact written pickup/drop-off details and map links on each manifest;
- copy a WhatsApp-ready plain-text manifest in one tap, download it as CSV or print a clean operational copy;
- review a persistent inbox for new bookings and service requests;
- prepare service quotes and update their operational/payment status;
- open prefilled WhatsApp or email confirmations for the customer.
- manage directional Adult, Pensioner, Student and Child fares without a code release;
- add, default, order or disable multiple pickup and drop-off points per town;
- review friendly non-blocking warnings for fare gaps, missing drop-offs and possible same-day duplicate departures;
- follow a plain-language Help centre designed for Boriza and future staff.

No password is stored in the repository or browser bundle. Production credentials live in encrypted Cloudflare Pages secrets.

The [Borizago Staff Guide PDF](https://borizashuttles.pages.dev/borizago-staff-guide.pdf) is deliberately public-safe: it demonstrates the operations flow without exposing passwords, customer records, payment proof or private credentials.

## Engineering

React, TypeScript and a server-side API run on Cloudflare Pages. Cloudflare D1 stores routes, trips, bookings, exact address snapshots, optional coordinates, service requests and admin notifications. Booking creation validates the selected segment, two distinct 10-digit contacts and both written locations, recalculates the fare on the server and reserves capacity atomically. Idempotency keys prevent repeated taps from creating duplicate records, while revision checks reject stale trip and admin edits.

Smart location support is deliberately customer-controlled: admin-approved meeting points appear immediately, address lookup runs only after the customer presses **Find this address**, and GPS runs only after **Use my current location**. Results are restricted to Namibia, attributed to OpenStreetMap, cached, and globally rate-limited; no background keystroke tracking or continuous location tracking is used.

Production now follows the same release path as the other SolarSpin projects: changes land on the private application's GitHub `main` branch, Cloudflare Pages builds a reproducible deployment package, and a successful build is promoted automatically to the existing Borizago project. The D1 binding and encrypted admin secrets remain in Cloudflare; neither the private application source nor those credentials are copied into this public case-study repository.

```mermaid
flowchart LR
  A[Browser or installed PWA] --> B[Cloudflare Pages app]
  C[Private staff dashboard] --> B
  B --> D[(Cloudflare D1)]
  A --> E[Customer-controlled WhatsApp actions]
```

Payment-pending bookings consume seats. Cancellation releases them. The service worker provides a clear offline page but never caches booking records, admin responses or seat availability.

## Security and reliability

- Server-generated, HttpOnly and Secure session cookies.
- HMAC-signed staff sessions with a 12-hour lifetime.
- Constant-time password comparison and server-side email allowlist.
- Caller-supplied identity headers stripped at the Cloudflare edge.
- Server-owned totals and atomic capacity enforcement.
- Server-side validation requires exact pickup/drop-off descriptions, a named alternative/emergency contact and a second phone number different from the primary number.
- Address lookup is explicit rather than background autocomplete; coordinates are stored only when the customer chooses to pin a location.
- No passenger data, credentials, banking details or database exports in this repository.
- Content-hashed frontend assets cached immutably; dynamic responses remain uncached.
- Mobile layouts verified at 320 px and 390 px with no horizontal overflow or header overlap.

## Current boundaries

Tours, airport transfers, private transfers and parcels now have complete request and staff-management flows. The admin Reports workspace provides monthly revenue, payment, trip and route summaries plus downloadable booking, customer and financial CSV ledgers. Customer phone numbers are enforced as exactly 10 digits at the browser and API boundary, two distinct numbers are required for every new request, and dates/times use explicit validated fields. Borizago captures customer-selected pickup/drop-off pins but does not continuously track people or vehicles. Card payments and fully automatic outbound email or WhatsApp remain external integrations. Staff can copy a complete manifest straight into a WhatsApp group and open prepared customer confirmations today; Zoho mail, Meta WhatsApp Business and a payment merchant can be connected later without replacing the core system.

## Repository boundary

This public repository contains case-study material only. Application source is maintained in a private repository. Brand assets belong to Boriza Shuttle & Tours.
