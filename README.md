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

The URL in a store listing points at `index.html` and must keep working, so:

1. Copy the current `index.html` to `<effective date>.html` — that file is then **never edited
   again**. A superseded version that can still change is not evidence of what users were told.
2. Write the new text into `index.html`, with a new version number and effective date.
3. Add the superseded version to the "Changes to this policy" section, so a reader can see what
   applied at any earlier point.

A typo or a clarification that does not change what is collected is not a new version: edit in
place and move the "Last updated" date only.

Old versions are kept indefinitely. Users stay on old app builds for years, and the text in force
when they installed is the one that describes their build; GDPR accountability (Art. 5(2)) expects
you to be able to show what you told people at a given time. It costs a few kilobytes.
