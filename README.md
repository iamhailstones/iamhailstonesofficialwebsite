# HAILSTONES — 3D Horror Portfolio

A static, single-file website (`index.html`). No build step, no backend, no API keys.

## Deploy to GitHub Pages
1. Create a repository and upload `index.html` and `README.md`.
2. Settings → Pages → Deploy from branch → `main` / root.
3. Open `https://<your-username>.github.io/<repo>/`.

## Edit links
All social links are in the `S` array near the top of the `<script>`.
**YouTube:** the channel URL could not be verified, so set `YOUTUBE_URL` to your real channel address. Until then the button opens a YouTube search for `iamhailstones`.

## The 3D scene (honest notes)
- Three.js r128 is loaded from cdnjs (pinned version). Needs internet; if it fails, the site shows a CSS horror fallback and stays fully usable.
- The man and his reaching hand are **procedural geometry** (head, glowing eyes that track the pointer, a multi-joint hand with finger movement, red/blue lighting, fog). They are atmospheric, not photorealistic. No realistic human model is bundled.
- For a photoreal character, add a licensed `.glb` model:
  1. Sources: Sketchfab (filter by downloadable), Quaternius, Poly Haven, Mixamo (check terms). Read the licence (CC0 / CC-BY are safest; credit if required).
  2. Prefer glTF/GLB, under about 5 MB, compressed (Draco/Meshopt) textures.
  3. Put it at `assets/models/man.glb`, add `GLTFLoader` from the Three.js r128 examples, and replace the `head` and `hand` groups with the loaded scene.
- Pixel ratio is capped (1.5 on phones), rendering pauses off-screen or in background tabs, and reduced-motion users get a still frame.

## Accessibility
Skippable intro, REDUCE EFFECTS button, `prefers-reduced-motion` support, visible focus, keyboard navigation, no hover-only features.

## Hero photo
The hero uses `assets/hero.jpg` (keep it in that folder). Make sure you own the photo or have the right to use it. The figure is the photo itself; Three.js only adds the reaching gloved hand, lights and particles on top.
