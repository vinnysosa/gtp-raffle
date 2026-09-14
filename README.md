# gtp-raffle

Public wrapper for the GTP 17U Tailgate Raffle buyer form, served by GitHub Pages at
https://gtp.sosa-life.com/raffle/.

The raffle itself is a Google Apps Script web app. Apps Script prints a "This application was
created by a Google Apps Script user" banner whenever `/exec` is the top-level document, and that
banner cannot be removed or scripted away from inside the app: the app renders in a sandboxed
iframe on `googleusercontent.com`, while the banner belongs to the `script.google.com` page around
it. Loading `/exec` inside this page suppresses the banner instead.

`raffle/index.html` forwards only a jersey number (`?n=53`). It never frames a caller-supplied URL,
so the page cannot be turned into a phishing frame for arbitrary content.

No player, parent, or buyer data lives in this repository. The application source is private at
`vinnysosa/personal-raffle-app`, and `web/index.html` there is the source of truth for
`raffle/index.html` — edit it there and copy the file over.
