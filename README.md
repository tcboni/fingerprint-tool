# Fingerprint Tool

A dashboard that shows you, live, what your browser silently
reveals about you — and how those weak signals combine into a near-unique
**fingerprint**. It collects the signals your device leaks, computes a single
fingerprint hash and an entropy estimate entirely in your browser, and explains
what each signal is and why it's identifying.

**[→ Open Fingerprint Tool](https://tcboni.github.io/fingerprint-tool/)**

## What it measures

- **Rendering** — Canvas fingerprint (with the rendered image shown), GPU / WebGL
  vendor, renderer, extensions and a render hash, and a CSS engine support matrix
  (~130 property, function, selector, at-rule and media-feature probes).
- **Signal processing** — Web Audio DSP fingerprint, floating-point math
  divergence, and installed-font detection.
- **Identity & hardware** — Navigator / User-Agent (incl. high-entropy Client
  Hints), screen & display, and a JavaScript-engine probe (timer precision,
  error wording, stack shape).
- **Environment** — timezone & locale, speech-synthesis voices, media-device
  counts, capability matrix (WebGPU, Bluetooth, USB, codecs, storage APIs…),
  network hints, CSS media preferences, and WebRTC local-network candidates.
- **Behavioral (live)** — a running histogram of your pointer/keyboard timing.

Each signal card shows the raw value, an entropy contribution meter, a tooltip
explaining what it is and why it leaks, and a copy button. The hero readout shows
your fingerprint hash, an estimated entropy in bits, and a plain-English verdict.
A "copy full report as JSON" button exports everything.

## A note on the numbers

Entropy figures are **heuristic estimates** drawn from public research
(EFF Panopticlick, AmIUnique, Mozilla), discounted for the correlation between
signals. They approximate how identifying each signal _tends_ to be — not a
measurement of the global browser population.
