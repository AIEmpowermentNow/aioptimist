# Video Provider Configuration

The Producer writes shot lists and prompts that are **provider-agnostic**. This file decides which engine actually renders them. To switch providers, change one line below. No skill file needs editing.

---

## ACTIVE PROVIDER: magnific

Change the line above to `higgsfield`, `runway`, `elevenlabs`, or `none` to switch. The Producer reads this line and nothing else.

---

## magnific

**Tools:** `mcp__Magnific_MCP__*`

**Pipeline:**
1. `images_generate` — render each keyframe from the shot list. One call per shot.
2. `creations_show` with the returned identifiers so the participant sees them inline, then `creations_wait` to confirm completion and get final asset URLs.
3. `video_generate` — pass the creation **identifier** (never the webUrl) into keyframes/references to animate each shot.
4. `audio_tts` — voiceover from the script, if the participant wants narration.
5. `video_concatenate` — stitch the shots into the finished reel.
6. `creations_show` on the final video.

**Rules:**
- Never regenerate a queued creation. Wait for it.
- Always `creations_wait` before chaining one output into the next tool.
- Never quote internal identifiers or UUIDs to the participant. Use names and links.
- If a participant has no local image to work from, `creations_upload_show` opens the upload widget. Never ask them to attach a file to chat.

**Credits:** each participant needs their own Magnific account. Before generating, tell them how many renders the shot list implies so nobody burns a trial on a first draft. Workshop attendees use the event signup link and code provided in the portal.

---

## higgsfield

**Tools:** `mcp__higgsfield__*`

Activate by changing the ACTIVE PROVIDER line to `higgsfield`. Bundled with this plugin as a remote connector, same as Magnific, so the participant signs in with her own Higgsfield account and the tools appear.

**Pipeline:** generate each keyframe from the shot list, then animate each shot from its keyframe, then assemble in order. Tool names vary by version, so read the connector's own tool list before the first call rather than assuming names. Poll any job-style call until it reports complete before chaining its output into the next step.

**If the connector is not connected**, fall back to handoff mode: produce the complete shot list, per-shot image prompt, per-shot motion prompt, voiceover script with timings, and assembly order as one copyable block, and say where each piece goes in the Higgsfield interface. Everything upstream of rendering is identical.

## runway

**Tools:** `mcp__Runway__*`

`generate_image` for keyframes, `generate_video` for motion, `generate_speech` for voiceover, `get_task` to poll. `generate_product_marketing_video` can do a single-call version for straightforward product reels — worth trying first for L1 and L2 lanes.

---

## elevenlabs

**Tools:** `mcp__elevenlabs__*` (bundled with this plugin as a remote connector)

Strongest when audio carries the piece. Call `creative_create_flow` FIRST when one generation feeds another, then pass that flow_id to every subsequent call. Poll `creative_get_flow_run_status` until complete. Voice must come from `creative_list_voices` or the participant — never invented.

---

## none

**No generation.** The Producer delivers the full Sizzle Brief — shot list, prompts, script, captions, assembly order — as a downloadable document, and says plainly that the participant can render it in whatever tool she already has, or film it on her phone. This is not a degraded path. The brief is the valuable part. Use this for anyone without credits, and for a cohort where no provider is confirmed.

---

## Choosing at runtime

Even with a provider active, the Producer should check that its tools actually respond before promising a video. If the provider is unreachable, say so in one sentence, fall back to `none` behavior, and keep moving. **Never let a missing video engine stall a participant at minute 40.** The brief is the deliverable. The video is the bonus.
