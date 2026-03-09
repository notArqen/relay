# relay · encrypted p2p chat

> a sleek, single-file chat application — encrypted, peer-to-peer, and ephemeral. no accounts, no servers, no trace.

---

## table of contents

- [overview](#overview)
- [features](#features)
- [getting started](#getting-started)
- [usage](#usage)
- [technical notes](#technical-notes)
- [license](#license)

---

## overview

**relay** is a fully self-contained, single HTML file chat application. no build process, no package manager, no backend — just one file you open in a browser and share a link. it's designed to feel like a proper messaging app without any of the surveillance infrastructure that comes with being one.

messages are encrypted on your device before they leave it. when the session ends, everything disappears. no logs, no history, no account needed. just open it, talk, close it.

---

## features

### messaging
- real-time peer-to-peer messaging via WebRTC
- end-to-end encrypted — messages are encrypted client-side before transmission
- ephemeral sessions — nothing is stored, nothing persists after you close the tab

### connection
- shareable session link generated on open — send it to whoever you want to talk to
- no account, no sign-up, no email verification, no "agree to our 47-page privacy policy and forfeit your first born child"
- direct p2p connection between participants — no server sitting in the middle reading your messages

### interface
- clean, minimal layout designed to stay out of the way
- responsive — works on desktop and (unstably) mobile
- **relay-mini** — a stripped-down lightweight variant for when even the standard version feels like too much

### privacy
- zero data retention — sessions leave no trace on any server
- no telemetry, no analytics, no third-party anything
- self-hostable — because trusting someone else's server with your "encrypted" chat somewhat defeats the purpose

---

## getting started

since relay is a single HTML file, setup is about as involved as opening a browser tab.

### prerequisites
- a modern browser (Chrome, Firefox, Edge, Safari — anything from the last few years)
- an internet connection (for WebRTC signaling on session start)
- nothing else

### running locally

```bash
# clone the repo
git clone https://github.com/notArqen/relay
cd relay

# open the file — that's it
open relayx.html
# or just drag it into your browser
```

### hosting it

since it's a single file, it runs anywhere static files are served:

```bash
# via GitHub Pages — push to repo, enable Pages in settings, done
# via any static host (Netlify, Vercel, Cloudflare Pages, etc.)
# or serve locally
npx serve .
```

then navigate to `relayx.html` and share the generated session url. relay is already hosted on github pages for your convienience.

---

## usage

### starting a session

open `relayx.html` in your browser. relay will generate a unique session link. copy it and send it to whoever you want to connect with. once they open the link, the session begins.

### sending messages

type in the message field and hit enter. messages are encrypted before leaving your browser and decrypted only on the other end. no intermediate server ever sees plaintext.

### ending a session

close the tab. the session is gone. no history is saved anywhere — not locally, not remotely. if you need a record of the conversation, that's on you.

### relay-mini

`relay-mini.html` is a minimal variant of relay — same core functionality, reduced interface. useful for embedding or lower-overhead use.

---

## technical notes

- **single file architecture** — all HTML, CSS, and JS live in `relayx.html`. no external dependencies, no build step.
- **p2p transport** — uses WebRTC for direct peer-to-peer data channels between participants.
- **encryption** — messages are encrypted client-side before transmission. the session is the key.
- **ephemeral by design** — no `localStorage`, no `IndexedDB`, no server-side persistence. when the session ends, it ends.
- **signaling** — a lightweight signaling step is required to establish the initial WebRTC connection. once connected, communication is direct.
- **unstable/** — experimental features live here. they may or may not work. proceed accordingly.

---

## license

[Apache 2.0](LICENSE) — open, permissive, and honest about it.

---

<p align="center">built with care.</p>
