# Privacy policies — GreenKey Universe

The published privacy policies for GreenKey Universe apps, served by GitHub Pages at
<https://safonov-a.github.io/privacy/>.

## Layout

```
<app>/<platform>/v<n>.html      the policy for a run of releases - what those builds link to
<app>/<platform>/index.html     a copy of the newest v<n>.html - what the store listing points at
```

Each app and platform gets its own document, because the same app can process different data on
different platforms. Schulte Table is the example: the Android build carries Firebase Auth,
Analytics, Crashlytics, Performance and Play Billing; the iOS build has no accounts, no analytics
and no crash reporting at all.

## Why the app links to a versioned file

A privacy policy has to be true about the software the reader is actually running. People stay on
old builds for years, and the URL is compiled into the binary — it cannot be changed afterwards. So
every build links to the document written for it, and that document keeps describing those
releases for as long as they are in use.

The documents are numbered `v1`, `v2`, … and the numbering is the file's own, not the app's. The
text deliberately names no version number: it says it describes the release that linked the reader
here, which stays true without maintenance. A marketing version moves for reasons that have nothing
to do with data - shipping 2.0 with no change to what is stored would otherwise strand a document
claiming to cover "1.x".

The store listing is different: it has one URL field and it must describe what a new installer
gets, so it points at `index.html`, which is always a copy of the newest `v<n>.html`.

Both files stay editable. That is the point of naming them by version rather than by date: when a
contact detail changes or something turns out to be described imprecisely, the correction has to
reach the people it applies to, including those on older builds.

## Issuing a policy for a new app version

Only needed when a release changes what the app stores or sends. A release that changes nothing
about data keeps the existing document and the existing URL.

1. Write `v<n+1>.html` describing the new release. Leave `v<n>.html` in place, still describing
   the releases that link to it.
2. Copy it over `index.html`, so the store listing describes the current release.
3. Link it from the site's landing page.
4. **In the same commit, change the URL constant in the app** — on iOS that is
   `PRIVACY_POLICY_URL` in `MainViewController.kt`.

Step 4 is the one that fails silently. Ship a release that collects something new while the
constant still points at the old document, and the app links to a text saying that data is not
collected. Nothing in the build catches it: it compiles, the URL resolves, the page loads. Keeping
the policy and the constant in one commit is what makes it hard to get wrong.

## History

The published history of every document is the git history of this repository, which is public: it
carries the date, the author and the exact diff of each change. There are deliberately no dated
snapshot files — they would duplicate that, and a file that may not be edited cannot also serve as
the policy someone's build links to.
