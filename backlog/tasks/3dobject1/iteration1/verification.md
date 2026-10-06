# Luffy verification — 2026-10-05

The colored character, editable project, and review renders were produced using Blender 5.2.2 LTS through the configured MCP connection. Technical export checks pass. Strict reference-match acceptance is **partial**, with the visual differences below.

## Artifact locations

Blender computer production root:
`C:/Users/Tomz/Documents/3dobject1/results/blender_work/`

- `final/luffy_colored.blend`: saved and reopened successfully; original, working, and GLB verification scenes included.
- `final/luffy_colored.glb`: 6,175,164 bytes; only the 21 intended character meshes exported.
- `renders/preview_match.png`, `preview_side.png`, `preview_back.png`, `detail_face.png`, and `detail_clothing.png`: native PNG renders, each decoded by Blender at 1024 × 1536.
- `renders/roundtrip_match.png`: render of the reimported GLB.
- `checkpoints/baseline.blend`, `regions.blend`, `materials.blend`, `luffy_basecolor.png`, and `luffy_normal.png`: recoverable checkpoints and authored textures. The final project contains the updated packed textures.

Local evidence: [final viewport](result-02.png), [face](renders/detail_face_viewport.png), [clothing](renders/detail_clothing_viewport.png), [side](renders/preview_side_viewport.png), [back](renders/preview_back_viewport.png). These are MCP viewport captures, distinct from the native portrait renders. The earlier `result.png` is preserved as an intermediate picture.

## Implementation

Preserved the original `Scene`, empty parent, and `tmp9o8wb20f.ply` mesh. Worked on independent mesh data in `3dobject1_Work`. Removed 19 confirmed long bridging triangles and filled four small boundary loops; the working mesh has 39,985 faces and zero nonmanifold edges. Pose and bounds were retained.

Built semantic selections from inspected garment outlines, surface-depth gates, tilted hat coordinates, ear landmarks, and cuff planes. Stored `semantic_region` face attributes and named material slots. Continuous surface masks were rasterized into a 2048 × 2048 UV color atlas, with authored weave variation and a separate tangent normal texture. Reviewed local PBR assignments correct hand, collar, and hat seams. The reference image was not projected onto the model.

Added fitted eyes, pupils, smile/teeth, chest and stitched cheek scars, and black sandal straps as separate named meshes. Existing jacket, buttons, shorts, cuffs, sash, hair, hat, and soles were retained and colored. Added isolated studio cameras, lighting, floor, and backdrop.

Comparison camera: orthographic, scale 2.14, position `(0, -5, 0.02)`, looking toward `(0, 0, -0.02)`. Its transform stayed fixed during material work. Source and GLB bounds agree: X `[-0.582313, 0.538080]`, Y `[-0.486917, 0.521770]`, Z `[-1.002175, 0.961739]`.

## Checks

| Check | Result |
| --- | --- |
| Local source GLB/reference hashes unchanged | Pass; hashes match initial records |
| Imported source preserved | Pass; 19,892 vertices, 40,000 faces, no materials or UVs |
| Exact imported provenance | User-confirmed; original GLB unavailable on Blender computer |
| Major pose, silhouette, clothing and color families retained | Pass, with source detail limitations |
| Facial details, scars and sandals inspected | Pass; local close-ups provided |
| Strictly clean boundaries and exact reference appearance | Partial; see remaining differences |
| Saved project opens with textures | Pass; both 2048px textures packed and readable |
| Final GLB reimport | Pass; 21 meshes, intended UVs and PBR materials retained |
| Exported base-color atlas fidelity | Pass; sampled pixel differences are exactly zero |
| Normal texture retention | Pass; 2048px non-color image retained |
| Local pictures | Pass; nonempty PNGs decoded and opened locally |
| Local model/native-render delivery | Unavailable; computers have no shared folder or exposed artifact transfer |

The first export contained stale packed PNG data after UV revisions. Comparing current, disk, and reimported images identified the mismatch. Removing the old image pack and repacking current PNGs fixed it; the final export was reimported again. Other viewers were not tested.

## Remaining differences

1. The source has simpler sculpted folds, cuffs, toes, fingers, and straw detail than the goal. No major reconstruction was performed.
2. Eyes, smile, and scars use fitted surface geometry; they remain flatter than the reference's sculpted features. Some close-up garment/contact boundaries need finer mask work.
3. A small irregularity remains at the back hat/hair junction. Texture detail and lighting approximate the reference rather than reproduce it exactly.

Native renders were decoded remotely and their camera views inspected through MCP. Their exact stored PNG pixels and model binaries were not transferred locally. No similarity percentage or full acceptance claim is made.
