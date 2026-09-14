# UpNews Privacy Policy — Android

Last updated: 14 September 2026 · Applies from app version 1.1.0 (build 2)

## Who is responsible for your data

**South Desert Studio, S.L.** (the "controller", "we", "us")

- Tax ID (CIF): B70875695
- Registered office: Calle Cigüeña Negra 1, Oficina South Desert Studio, 04230 Huércal de Almería,
  Almería, Spain
- Contact for anything in this policy: `hola@southdesertstudio.com`

Full company identification is in the [UpNews Legal Notice](upnews-android-legal-notice.md).

This policy covers the Android app **UpNews**, published on Google Play with the package name
`com.southdesertstudio.upnewsapp`, and the UpNews content service the app talks to. The iOS app has
its own policy. It is written to comply with Regulation (EU) 2016/679 (GDPR) and Spanish Organic Law
3/2018 (LOPDGDD).

## Summary

- No account, no sign-in, no advertising, no analytics and no crash-reporting software.
- The app does not read your name, email, contacts, photos, files, microphone or camera.
- What leaves your device is limited to what is needed to show you content: your **approximate
  location** (rounded to about 1 km), your **app language**, the **topics** you choose and, if you
  use the horoscope topic, your **chosen zodiac sign**. In one fallback case your **IP address** is
  used to estimate an approximate area.
- None of this is tied to an identity, sold, or used to build a profile.

## Permissions the app requests

| Permission | Why | When |
|---|---|---|
| `INTERNET`, `ACCESS_NETWORK_STATE` | Download news, weather, topic content and images | Always |
| `ACCESS_COARSE_LOCATION` | Show weather for your area | Only while the app is open, only if you grant it |
| `FOREGROUND_SERVICE`, `FOREGROUND_SERVICE_MEDIA_PLAYBACK` | Keep a spoken briefing playing when you leave the screen | Only during a briefing you start |
| `WAKE_LOCK` | Stop the device sleeping in the middle of a briefing | Only during a briefing you start |

UpNews does **not** request precise location, background location, notification posting, exact
alarms, boot completion, contacts, calendar, camera, microphone, phone state or storage access. You
can revoke location at any time in Android Settings; the rest of the app keeps working.

## What leaves your device, to whom, and why

### 1. Approximate location → UpNews service → weather providers

When you have granted location, the app asks Android for an approximate position (from the network,
or from the fused or GPS provider on Android 12 and later — always limited by Android to coarse
accuracy). Before anything is sent, the app **rounds the coordinates to two decimal places (about
1.1 km)**. The UpNews service rejects more precise values.

The UpNews service uses those rounded coordinates only to fetch the forecast:

- **In Spain**, it looks up the nearest municipality locally and asks **AEMET** (Spanish State
  Meteorological Agency) for that municipality's forecast. AEMET receives the municipality code,
  not your coordinates. If AEMET fails, **Open-Meteo** receives the rounded coordinates.
- **Outside Spain**, **XWeather** receives the rounded coordinates; if it fails, **Open-Meteo** does.

The app keeps your last approximate position on the device for up to seven days so it does not have
to ask Android again every time. No history or movement track is created, on the device or on the
server.

### 2. IP address → `ipwho.is` (fallback only)

If you have granted location but Android cannot provide a position after three attempts, the app
asks the third-party service **`ipwho.is`** to estimate an approximate area from your IP address.
That service receives your IP address as part of the request. If you have not granted location, or
your device provides a position, this request never happens.

### 3. Content preferences → UpNews service → content providers

To show the cards you selected, the app sends to the UpNews service:

- your **app language** (English or Spanish), sent on to NewsData.io, APITube and JokeAPI so they
  return content in that language;
- the **topics and news categories** you have switched on;
- for the horoscope topic only, the **zodiac sign you picked** and today's date, sent on to
  AstroWay. The app never asks for your date of birth.

Topics such as technology, space, art, football and markets are requested without any data about
you.

### 4. Image downloads → news publishers' image servers

Article images are downloaded by the app directly from the server that hosts them (usually the
news publisher's content delivery network). As with any internet request, that server sees your IP
address. No cookies or identifiers are sent with these requests.

### 5. Connection metadata

Every HTTPS request reveals your IP address and basic technical information (such as the time of
the request) to the server that receives it. This applies to the UpNews service, `ipwho.is` and
image servers. The app adds no advertising ID, device ID or cookie to any request.

## What never leaves your device

Smart Elevator sensor readings (acceleration, gravity, barometric pressure) and their aggregates,
spoken briefing audio, your reading position and your settings other than those listed above are
never transmitted.

## Device sensors and Smart Elevator

Smart Elevator reads linear acceleration, gravity and, when available, barometric pressure through
Android's standard sensor framework. Raw samples exist only in memory and are discarded when the
check stops; only bounded aggregates are stored on the device.

## Spoken briefing

The briefing uses the text-to-speech engine installed on your device. The generated audio is stored
in app-private storage, excluded from backup, and deleted when the briefing ends, is invalidated or
after six hours. The playback notification contains no article text, location or links.

Some text-to-speech engines that you may have chosen in Android Settings can use an online voice. In
that case the text being read is processed by that engine's provider under its own privacy policy;
UpNews does not control or receive that processing.

## Links you open

Opening an article, a source or one of these legal documents hands the link to your web browser.
From then on you are on a third-party website (for legal documents, GitHub), which applies its own
terms and privacy policy. UpNews contains no embedded web browser and sets no cookies.

## Legal bases (GDPR Article 6)

| Processing | Legal basis |
|---|---|
| Delivering the news, weather and topic content you request, including sending language, topics and zodiac sign | Art. 6(1)(b) — providing the service you asked for |
| Using approximate location for local weather | Art. 6(1)(a) — your consent, given through the Android location permission and revocable at any time |
| IP-based approximate area when location fails | Art. 6(1)(f) — legitimate interest in providing weather when the permission path fails, limited to an approximate area |
| Downloading images and keeping the service secure and working | Art. 6(1)(f) — legitimate interest |

## Recipients

We do not sell, rent or share personal data for advertising or marketing. Data reaches only these
recipients, for the purposes above:

| Recipient | Role | What it receives |
|---|---|---|
| Cloudflare, Inc. | Hosts the UpNews service (processor) | Requests to the service, including rounded coordinates, language, topics and sign |
| AEMET | Weather provider (Spain) | Municipality code |
| Open-Meteo | Weather provider | Rounded coordinates |
| XWeather (Vaisala) | Weather provider (outside Spain) | Rounded coordinates |
| `ipwho.is` | IP geolocation (fallback only) | IP address |
| NewsData.io, APITube, JokeAPI | Content providers | App language, news category |
| AstroWay | Horoscope provider | Zodiac sign, date, language |
| News publishers' image servers | Image hosting | IP address (network level) |

Providers other than Cloudflare receive the request from the UpNews service, not from your device,
so they do not see your IP address, except `ipwho.is` and image servers, which your device contacts
directly.

## International transfers

Cloudflare runs the UpNews service on its global network, so a request may be processed outside the
European Economic Area. Some providers above (for example XWeather, NewsData.io or `ipwho.is`) may
process requests outside the EEA. Where a transfer takes place, it relies on an adequacy decision
(including the EU–US Data Privacy Framework for certified companies) or on the European
Commission's standard contractual clauses offered by the provider.

## How long data is kept

- **UpNews service:** no account and no request history linked to you. To reduce load, responses are
  cached on Cloudflare's network under a key built from the request (for weather: rounded
  coordinates and language; for horoscope: sign, date and language). The cache entry expires at the
  latest at the next midnight UTC. The service does not write application logs containing request
  data.
- **Cloudflare** may process connection data for security and network operation under its own terms.
- **On your device:** settings, your last approximate position (up to seven days), bounded Smart
  Elevator aggregates, and cached content and images stay until they are replaced through normal use
  or you uninstall the app. Automatic backup and device-to-device transfer are disabled, so Android
  does not copy this data to the cloud.

## Your rights

Under the GDPR you can ask for access, rectification, erasure, restriction, objection and
portability, and you can withdraw consent at any time without affecting earlier processing. Write to
`hola@southdesertstudio.com`. We will answer within one month.

Because the app has no account and keeps your data on your own device, the quickest way to erase
everything is to revoke location in Android Settings and uninstall the app. We cannot link any
request received by the service to you.

You can complain to the Spanish supervisory authority, the **Agencia Española de Protección de
Datos** (`www.aepd.es`), or to the authority in your country of residence.

## Automated decisions

UpNews makes no decisions about you based solely on automated processing that produce legal or
similarly significant effects.

## Features currently disabled

This version ships with on-device translation and full-article web scraping switched off. If a
disabled feature is enabled in a future version, this policy will be updated before that version is
released.

## Children

UpNews is not directed to children under 14 and does not knowingly collect data from them.

## Changes

If this policy changes materially, the new version will be published at the same address with a new
date before the change applies.
