# Chromia

Point your phone's camera at something — a flower, a leaf, a wall — and get
back the color name and hex value. Built for plein air painting reference.

**Live:** https://cillianslayde.github.io/chromia/

---

## What it is

- Live camera viewfinder with a center crosshair — tap Capture to sample the
  color under it
- Prefers the rear/environment camera automatically
- Two backup input modes if camera access isn't available: **Describe**
  (type a description) and **Hex** (enter a hex code directly)
- Alternate **network stream** source mode (MJPEG) for setups where a
  browser camera isn't available or permitted

Everything runs client-side — no build step, no account, nothing installed.

## Camera permissions require HTTPS

Browsers only allow camera access (`getUserMedia`) on a "secure context" —
`https://` or `localhost`. The hosted GitHub Pages link above is `https://`,
so camera access works there without any workaround.

## A known limitation of Network Stream mode

Color sampling only works on the native browser camera. If you switch to
Network Stream mode (e.g. an IP Webcam/DroidCam feed on your LAN), the video
preview still works, but tapping Capture will tell you sampling isn't
available in that mode — this is a browser security restriction (reading
pixel data off a cross-origin video feed is blocked), not a bug, and can't
be worked around without the streaming server sending CORS headers, which
consumer IP-camera apps generally don't. Use Describe or Hex mode instead if
you're on Network Stream and need a color.

## Running it

Open `index.html` in any modern mobile or desktop browser (Chrome, Edge,
Firefox, Safari) — or just use the hosted link above.

## License

All Rights Reserved — see [LICENSE](./LICENSE). Free to use as-is via the
hosted link above; not licensed for redistribution or reuse of the source.
