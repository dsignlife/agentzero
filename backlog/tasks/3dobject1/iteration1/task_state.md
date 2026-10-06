# Luffy finishing execution

Spec: [task1.md](../../task1.md). Production directory: this `blender_work/` directory.

## Confirmed inputs and boundaries
- User confirms the current imported mesh is `white_mesh.glb`.
- Original scene contains `Luffy Current Structure` and `tmp9o8wb20f.ply`; preserve both.
- Blender 5.2.2 LTS is reachable through `blender`. Addon status has an independent missing `blender_mcp.config` error; scene and execution tools work.
- Mesh: 19,892 vertices, 40,000 triangles, one connected component, no boundary or nonmanifold edges, no materials or UVs. Coordinate height is Z; figure faces approximately -Y.
- Local input SHA-256 values match the Director's recorded GLB and reference hashes.
- Local input paths are inaccessible on the Blender computer. The reference is inspected locally; the user's confirmed imported mesh is the operational source.
- Output-folder mapping requested; pending. No infrastructure changes or custom transfer workarounds.
- `planning-with-files` is absent from the available catalog and filesystem search. Use this single task ledger with the supplied eight-phase plan instead. No helper execution files.

## Execution stages and checks
- [x] Preserve source in original scene; independent task scene, baseline cameras and checkpoint saved remotely.
- [x] Fix comparison camera; document source limitations in verification.md.
- [x] Build and review revisable semantic regions, UV masks and face attributes.
- [x] Add fitted focal details and repair confirmed bridging artifacts; preserve pose and bounds.
- [x] Apply PBR materials, authored color and normal textures; pack current images.
- [x] Correct major region leakage and inspect side/back coherence. Strict clean-boundary gate remains partial.
- [x] Save and reopen project; export 21 intended meshes and reimport final GLB with matching sampled atlas pixels.
- [x] Save native portrait PNGs remotely and readable viewport PNGs locally; report delivery and visual limitations.
- [ ] Full strict reference-match acceptance: residual contact boundaries, back hat seam and finer source detail differ from the target.

## Latest state
Production is saved under `C:/Users/Tomz/Documents/3dobject1/results/blender_work/` on the Blender computer. The user confirmed the computers do not share a folder. The final project was reopened with packed textures; the original scene remains recoverable. Final GLB is 6,175,164 bytes, contains 21 meshes, and passed repeated round-trip checks after a stale packed-image correction.

Local final evidence is `result-02.png` and four `renders/*_viewport.png` files, with passed/partial/unavailable checks in [verification.md](verification.md). No model binary or native portrait render was transferred locally. The Blender UI is restored to the working comparison camera in rendered shading. No Git commit, infrastructure change, paid service, publication or print action occurred.
