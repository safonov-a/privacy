# Privacy policies — GreenKey Universe

The published privacy policies for GreenKey Universe apps, served by GitHub Pages at
<https://safonov-a.github.io/privacy/>.

## Layout

```
<app>/<platform>/index.html      the policy in force — this URL never changes
<app>/<platform>/<date>.html     a superseded version, kept verbatim
```

Each app and platform gets its own document, because the same app can process different data on
different platforms. Schulte Table is the example: the Android build carries Firebase Auth,
Analytics, Crashlytics, Performance and Play Billing; the iOS build has no accounts, no analytics
and no crash reporting at all.

## Changing a policy

Every version is published at **two** addresses at the same moment: `index.html`, which the store
listing and the shipped apps point at and which therefore must keep working, and `<effective
date>.html`, which is never touched again. Publishing both together is what keeps the archive from
depending on anyone remembering to copy a file before overwriting it.

To issue a new version:

1. Write the new text into `index.html` with a new version number and effective date, and add the
   new version to the list at the end of "Changes to this policy" — keeping every earlier entry.
2. Copy the finished `index.html` to `<effective date>.html`.
3. Link the new version from the site's own landing page.

Never edit a dated file afterwards. A superseded version that can still change is not evidence of
what users were told. Note what this means for wording: no page may describe itself as "current",
because the same bytes are also the archived copy — instead every version states, in its header,
the one address at which the version in force is always published.

## Old app versions are still in use, and the policy must stay true for them

Every released build links to `index.html` — the URL is compiled into the binary and cannot be
changed afterwards, and a store listing has one such field. So whatever is published there is what
someone running a two-year-old build reads.

**A policy that describes only the newest release is therefore wrong for everyone who has not
updated.** The direction of the error matters less than people assume: a text that understates
collection hides processing that is actually happening, and a text that overstates it tells someone
their app does something it does not. Both are false statements to a user about the software on
their device.

So when a new app version changes what is stored or sent, the policy says what **each** version
does, keyed by app version, and keeps saying it for as long as the older ones are in use. A
description is only dropped once the version it covers is no longer plausibly installed anywhere.

This is a different axis from the dated files, and the two are easy to confuse:

| | What it is | Changes? |
| --- | --- | --- |
| `index.html` | what is true of every version in use, today | yes — corrections and new app versions |
| `<date>.html` | what was *published* on that date | never |

The dated copies are evidence of what users were told. They are not per-version policies, and the
app must not link to one: someone on an old build needs the current, corrected description of their
version, not a frozen page that can no longer be fixed.

A typo or a clarification that does not change what is collected is not a new version: edit in
place and move the "Last updated" date only.

Old versions are kept indefinitely. Users stay on old app builds for years, and the text in force
when they installed is the one that describes their build; GDPR accountability (Art. 5(2)) expects
you to be able to show what you told people at a given time. It costs a few kilobytes.
