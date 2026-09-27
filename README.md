# Theme_reveal

A standalone AI command-lab experience. Wave to wake the cat agent, point to direct its gaze, show an open palm to scan, pinch to manipulate the holographic field, then raise and hold two distinct hands to trigger the reveal. The realistic cat portrait was cut from the supplied video and is displayed in the Three.js scene with the existing lift and celebration motion. Canvas draws the lab backdrop and effects; MediaPipe Hands tracks gestures. An original procedural score combines ambient chords, a brighter rhythmic arpeggio, echo, and gesture cues. The supplied ElevenLabs recording plays only its opening greeting on the first wave, then plays the remainder when both hands activate the sequence. No browser-generated speech is used. Music automatically lowers during the recording, and a confetti burst and popper sound mark the reveal. Audio begins after clicking **Activate Sensor**.

The neutral still extracted from the supplied 10-second video is at `assets/cat-video-frame-reference.jpg`; its transparent cutout is `assets/cat-cutout.png`. The source is a still, so eye tracking and limb animation are not visible on the photo, while gesture responses, overall movement, and the HUD remain active. The voice clip is split at 4 seconds; adjust `greetingEndSeconds` in `index.html` if the greeting ends at a different point in the recording.

## Run locally

From the repository root, start a local static server in this folder:

```sh
cd mlsc-agent-lab
python3 -m http.server 8000 --bind 127.0.0.1
```

Then open <http://localhost:8000> in Chrome or Edge and allow camera access. Use the `localhost` URL exactly; `http://[::]:8000` is not treated as a trusted local origin by some browsers, so camera APIs can be unavailable there. Internet access is needed to load MediaPipe from jsDelivr.

This standalone browser prototype loads MediaPipe Hands and Three.js from jsDelivr and uses Canvas for the background effects. It does not use OpenCV; OpenCV is only relevant to a separate Python-based implementation.

## Higher-detail character options

For a future fully rigged 3D replacement, review the [rigged PBR cat on Sketchfab](https://sketchfab.com/3d-models/female-cat-c2443b5303164b17bbc8982770e4cabe). Its listing reports about 532k triangles and a CC BY license, so it would need optimization and visible attribution before use. A lighter reference is [Clint Catswood the Tabby](https://booth.pm/ja/items/8566295) (about 93k triangles, rigged GLB), but its creator's terms restrict editing and redistribution, so it is not a suitable drop-in asset for this web app.
