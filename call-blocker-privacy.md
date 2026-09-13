---
layout: default
title: ABS Call Blocker Privacy Policy
---

# ABS Call Blocker — Privacy Policy

**Last updated: 13 September 2026**

ABS Call Blocker is an Android app that rejects incoming calls matching rules you
define, and keeps a record of the calls it blocked. This policy explains what the
app does with your information.

In short: **the app has no server, no account, and no analytics. Everything it
knows stays on your phone, except an optional backup that goes to your own Google
Drive.**

## Who this covers

This policy covers the ABS Call Blocker Android app (package
`com.abs.callblocker`), distributed as a signed APK. It does not cover Google
Drive or any other service you use alongside it — those have their own policies.

## What the app accesses, and why

| What | Why | Optional? |
|---|---|---|
| **Call screening role** (`ROLE_CALL_SCREENING`) | This is how Android lets the app see an incoming call and decide whether to reject it. It is the app's core function. | Required for blocking |
| **Your contacts** (`READ_CONTACTS`) | Only to show a contact's name next to a number, and to fill in a rule from a picked contact. The app reads *only* the contact you pick or the one matching a number that already called you. | Optional — the app works without it, showing numbers instead of names |
| **Your Google Drive** (scope `drive.file`) | Only if you turn on backup. See below. | Optional — off by default |
| **Internet** | Only used to talk to Google Drive for the optional backup. The app makes no other network calls. | — |

The app does **not** request `READ_CALL_LOG` or `WRITE_CALL_LOG`. It never reads or
writes your device's system call history. It keeps its own separate record of the
calls it blocked.

## What the app stores

Everything below is stored **only on your device**, in the app's private database:

- **Blocked calls** — the phone number that called, the matching contact's name (if
  contacts access is granted), and the time of the call.
- **Block rules** — the number or prefix you entered, its label, and an optional
  contact name.

The app also stores three small settings: whether backup is on, when it last ran,
and the last Drive status. These contain no personal data.

## What the app never does

- No account and no sign-in.
- No server operated by the developer. The app has no backend, and none of your
  data is sent to the developer or to any third party.
- No analytics, no crash reporting, no advertising, no tracking, no advertising ID.
- No access to your location, your files, your photos, or your device identifiers.
- No selling or sharing of your data. There is no data to sell — it never leaves
  your device except to your own Drive, if you ask it to.

## Optional backup to your Google Drive

Backup is **off by default**. It runs only after you turn it on and approve
Google's permission prompt.

When enabled, the app writes a single file named `ABS-CallBlocker-backup.json` into
your own Google Drive, and every later backup overwrites that same file. The file
contains your block rules and your blocked-call history — including phone numbers
and any contact names resolved for them.

Things worth knowing:

- **The backup file is plain text, not encrypted.** Anyone who can already read your
  Google Drive can read it. This is deliberate — the file is yours, in your storage,
  and you can open it.
- **The app uses the narrowest Drive permission Google offers** —
  `drive.file` — which lets it see only the files it created itself. It cannot see,
  read, or modify anything else in your Drive.
- **No access token or refresh token is stored.** The app gets a one-hour access
  token each time it needs one. It cannot reach your Drive at any other moment.
- **The developer never sees this file.** It goes from your phone to your Drive, and
  nowhere else.
- **You can delete it at any time** by deleting `ABS-CallBlocker-backup.json` in
  Google Drive, or by turning backup off in the app. Deleting the file does not
  affect the copy on your phone.

## Android's own device backup

Like most Android apps, ABS Call Blocker allows Android's built-in backup service to
include its app data (the blocked-call records and rules) in your device's own cloud
or device-transfer backup. That backup is created and controlled by Android and your
Google account, not by this app. You can turn it off in Android's system settings
under Backup.

## Retention and deletion

- Blocked calls are **kept until you remove them** — by uninstalling the app, or by
  restoring from a backup, which replaces all local data. Individual blocked calls
  cannot currently be deleted one by one.
- Block rules can be deleted individually at any time from the app.
- The Drive backup file is kept until you delete it in Drive. Each backup overwrites
  the previous one, so it does not accumulate copies.
- Uninstalling the app removes its local database from your device (subject to
  Android's own device backup, above). It does not delete the file in your Drive —
  remove that in Drive if you want it gone.

## Children

The app is a general-purpose call-blocking utility, is not directed at children, and
does not knowingly collect information from them.

## Changes to this policy

If this policy changes, the updated version will be posted at this address with a new
"last updated" date. Material changes will also be noted in the app's release notes.

## Contact

Questions about this policy or about the app's data handling:
[github.com/abhisheksarkar30](https://github.com/abhisheksarkar30)
