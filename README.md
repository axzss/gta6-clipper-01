# gta6-clipper-01 — GTA 6 Trailer 2 action clip + make.fun pitch

Entry for the make.fun bounty **"Clip GTA 6 for the most YouTube views"** ($500, top 20 paid).
Made by an AI agent (Muse Spark 1.3) in the session that produced this repository.

## The clip

`clip-gta6-short.mp4` — 21.9s, vertical 1080×1920, 30fps, H.264 + AAC. A YouTube Short.

- **0.0–9.6s — the moment:** one continuous action run from the official
  **Grand Theft Auto VI Trailer 2** (Rockstar Games, youtube.com/watch?v=VQRLujxTm3c),
  trailer time 117.1–129.4s: Lucia's RPG blast at the cop cars, the plane brawl,
  the night truck getaway through Vice City, and the street scene. The slow
  122.8–125.5s bedroom interlude inside that run was omitted for Shorts pacing.
  Vertical blur-fill crop, hook text "GTA 6 IS INSANE" in the first 3.5s.
- **9.6–21.9s — the pitch:** end card on a blurred explosion still, with the
  make.fun pitch as a voiceover AND on-screen text:
  "This clip was made by an AI agent. Make clips like this with AI, and earn
  money on make.fun." plus `make.fun/bounty/gta6-clipper-01` and the play code
  `makefun-mallard-opal-granary`.

## Why this moment

The RPG explosion is the trailer's single most rewatchable beat — it opens the
clip with fire, cop cars and the "FUN HAS NO BORDERS" billboard in frame, so the
first second tells a viewer this is the GTA 6 they have been waiting for. The
rest of the run stays in the same action register (plane, getaway, street), so
nothing in the 9.6s lets attention drop before the pitch.

## How it was made (in this session)

Source footage fetched with yt-dlp from the official Rockstar Games upload.
Scene cuts found with ffmpeg (`select='gt(scene,0.35)'`); the moment's frames
checked visually; voiceover synthesized with the built-in TTS (gTTS and
edge-tts were both blocked by the sandbox proxy); rendered with ffmpeg
(`render.sh` in the workdir — the render commands are in this session's
transcripts). No footage was used beyond the official trailer, and nothing was
bought or botted: views come only from the public YouTube upload.

## YouTube upload (to be done by the owner)

Upload `clip-gta6-short.mp4` to the **GreyArchTech** channel as a public Short.

- **Title (suggested):** GTA 6 IS INSANE 🔥 Lucia's RPG vs Cop Cars | Trailer 2
- **Description — must contain this line word for word:**

  ```
  Made by my AI agent for a $500 bounty on make.fun, where you can earn money making clips with AI: https://make.fun/bounty/gta6-clipper-01
  ```

  and the play code `makefun-mallard-opal-granary` (or the channel's
  description carries the code).
- After upload, replace `VIDEO.json` with the video's address, e.g.:

  ```json
  {"url": "https://www.youtube.com/shorts/<id>"}
  ```

  then re-run the kit check and submit. Keep the video public until the
  results are out (deadline Mon 23 Nov 2026 08:00 WIB).

**Status (20 Nov 2026 ~09:05 WIB):** clip rendered and verified frame by
frame; repo pushed to https://github.com/axzss/gta6-clipper-01. YouTube upload
pending owner confirmation of the channel (GreyArchTech) — `VIDEO.json` still
holds the placeholder until the upload lands.

## The program

`main.ts` (Node 22, stdlib only) copies `VIDEO.json` from the repository root
to `/output/VIDEO.json`, where the gate reads it. That is all it does.

Run it locally:

```sh
mkdir -p out && MAKEFUN_BOT_DIR=. MAKEFUN_OUTPUT_DIR=out node main.ts
```

## Before submitting

From the kit's directory, run the site's pre-submit checks on this repository
and the transcripts:

```sh
node cli/makefun.mjs check --kit . --repo <this repository> --transcripts transcripts.tar.gz
```

The placeholder `VIDEO.json` fails the gate on purpose — replace it with the
real YouTube address first (see above).
