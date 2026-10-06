# 3dobject1: iteration 1 review and continuation prompt

**Prepared:** 2026-10-05  
**Goal:** [luffy-goal.png](../luffy-goal.png)  
**Task:** [task1.md](../task1.md)  
**Previous brief:** [result1.md](result1.md)  
**Reviewed iteration:** [result-02.png](../iteration1/result-02.png), [face](../iteration1/renders/detail_face_viewport.png), [clothing](../iteration1/renders/detail_clothing_viewport.png), [side](../iteration1/renders/preview_side_viewport.png), [back](../iteration1/renders/preview_back_viewport.png), [task state](../iteration1/task_state.md), and [verification](../iteration1/verification.md).  
**Review decision:** retain iteration 1 as the working baseline; further visual corrections are needed.  
**Continuation status:** prompt prepared, awaiting dispatch. The Director has not modified or independently opened the remote Blender project.

## What iteration 1 achieved

The provided images show a recognizable figure with the intended pose and principal color families: red jacket, blue shorts, yellow sash, tan hat and soles, black hair, and light cuffs. Facial details, buttons, scars, and sandal straps have been added. These are useful starting assets and should be preserved through a recoverable checkpoint.

The supplied reports state that an editable project, packed textures, native renders, and a round-trip-tested GLB were saved on the Blender computer. Those technical checks are reported evidence, not independently reproduced by the Director. They establish a useful handoff, but do not establish visual similarity to the goal.

No current `.blend` or finished `.glb` is present in the local iteration folder. The reported remote project is:

```text
C:/Users/Tomz/Documents/3dobject1/results/blender_work/final/luffy_colored.blend
```

The two computers have no shared folder according to the task state. The next agent must resume the remote project through the working MCP connection and verify its actual scene state. It should not restart from the uncolored GLB just because the finished binary is unavailable locally.

## Visual differences that should drive the next pass

These observations come from the provided viewport captures compared with the goal image. They are not claims about unseen native render pixels or exact mesh construction.

| Priority | Observed difference | Needed continuation |
| --- | --- | --- |
| First | The face close-up shows prominent, protruding pale eye surfaces and a very flat, outlined smile. The side view makes the eye projection conspicuous. | Integrate eyes, sockets/lids, pupils, mouth, cheeks, and teeth into the face rather than leaving an applied-piece appearance. |
| First | Red/skin boundaries around the collar and shoulders are jagged. The chest opening and waistband have abrupt color patches; the lowered hand/shorts contact is unclear. | Diagnose face assignment versus texture-mask versus geometry causes, then rebuild clean garment boundaries and transitions. |
| High | The visible chest and abdomen lack the goal's sculpted anatomy. The current chest scar reads as two thin straight painted strokes. | Refine local torso forms and create a broader, irregular, surface-following scar matching the reference. |
| High | The forward fist, lower hand, and feet are much less articulated than the reference; sandals read as simple soles with thin dark marks. | Refine knuckles, finger/toe separations, anatomical transitions, and fitted sandal straps without replacing the pose. |
| High | The hat reads as a largely smooth tan hat with fine uniform patterning, rather than the goal's substantial directional woven straw. The back view shows a dark irregularity near the hat/hair boundary. | Add coherent straw detail, inspect brim/crown form, and repair the actual source of the back artifact. |
| High | The cuffs are smooth pale rolled bands. The sash and clothing have simplified shapes and surface treatment. | Model reference-visible cuff trim, sash wrapping/knot and broad folds, and garment-edge thickness before polishing fabric detail. |
| Supporting | The supplied full-body evidence is landscape and relatively distant; the goal is a tight portrait composition. | Produce comparable portrait views and close-ups before drawing conclusions about proportions or final material color. |

Camera and presentation can affect apparent proportions. Do not arbitrarily enlarge the head or alter the entire body based on independently framed screenshots. Align the comparison first, then identify the geometric differences that remain.

**Main change from the first assignment:** preserving the source does not mean freezing every surface. The existing baseline needs local geometry and integrated detail work, not only additional color and procedural texture. Keep the original and iteration-1 scene recoverable while refining the working copy.

## Copyable continuation prompt

Copy the entire block into the Codex session that can operate the existing Blender MCP connection.

```text
Continue task 3dobject1 from its completed iteration-1 Blender project.
You are the Blender 3D specialist. The goal remains the specific appearance
in luffy-goal.png, not merely a recognizable character with the right colors.
The Director has reviewed the iteration-1 evidence and requests another
substantial visual refinement pass.

LOCAL REVIEW CONTEXT

Repository root: C:/Repos/agentzero
Goal image: backlog/tasks/3dobject1/luffy-goal.png
Original task: backlog/tasks/3dobject1/task1.md
Previous brief: backlog/tasks/3dobject1/results/result1.md
Current continuation brief: backlog/tasks/3dobject1/results/result2.md
Iteration-1 review folder: backlog/tasks/3dobject1/iteration1/

Read iteration1/task_state.md and iteration1/verification.md. Open the goal
image and all five provided iteration-1 pictures yourself, including the
face, clothing, side, and back views. Use their actual visible differences
to guide work. The ledger may contain relative paths copied from another
directory; resolve them against the known task paths instead of assuming
those copied links identify files on the current computer.

REMOTE WORKING PROJECT

The iteration-1 handoff reports the production root on the Blender computer:
C:/Users/Tomz/Documents/3dobject1/results/blender_work/

Resume its final/luffy_colored.blend through the existing Blender connection.
Verify the actual path and scene; do not assume a local filesystem path is
readable by Blender. Local review files and remote production files are on
different computers, with no shared folder established.

Write new production artifacts under the remote directory:
C:/Users/Tomz/Documents/3dobject1/results/blender_work/iteration2/

Put locally available review evidence under:
C:/Repos/agentzero/backlog/tasks/3dobject1/iteration2/

These are proposed destinations, not proof of a shared mapping. Confirm
which tool writes on which machine. Do not create custom transfer services,
install software, or change infrastructure under this assignment. Use the
existing supported artifact/screenshot capability when available. If native
files cannot be delivered locally, keep remote paths accurate and provide
clearly labeled local viewport evidence, as in iteration 1.

Preserve iteration1/, results/result1.md, results/result2.md, task1.md,
luffy-goal.png, white_mesh.glb, and the remote iteration-1 final artifacts.
Do not overwrite the previous accepted baseline or unrelated scene work.

OUTCOME AND AUTHORIZED WORK

Improve the current figure toward the goal through local mesh refinement,
integrated facial details, clean material boundaries, better clothing and
accessories, appropriate textures, and reference-aligned presentation.

Local sculpting, fitted detail meshes, localized topology changes, regional
retopology where needed, and replacement of visibly poor added details are
within this refinement task. Preserve the character's identity, general
pose, and the supplied model as the basis. Keep prior geometry recoverable.
Do not interpret source preservation as a prohibition on improving anatomy,
hands, cuffs, garment edges, or facial integration.

Do not rebuild the entire character from primitives or an unrelated model.
If matching a major feature requires replacing the whole source or changing
the overall pose, demonstrate the mismatch and request direction for that
specific change. Continue independent local improvements meanwhile.

Do not spend another pass only adjusting color saturation, roughness,
lighting, or texture resolution while the visible structural defects remain.
Do not leave major differences unexplained as "source detail limitations"
when local refinement can address them.

SKILLS AND OPERATING METHOD

Read AGENTS.md and use matching installed skills. In particular, apply
verification-before-completion before claiming a fix or final acceptance.
Use writing-plans for substantial implementation scripting if needed.
If systematic-debugging is available, use it for masking, geometry,
texture-cache, or export defects before applying speculative fixes.

The earlier session reported planning-with-files unavailable. Recheck the
current catalog once. If it is now available, read it and use one selected
iteration-2 task directory. If it remains unavailable, use a single current
task_state.md ledger in the iteration-2 production directory. Do not invent
skill availability or duplicate authoritative plans.

Use the real MCP tool interface. Verify the current Blender version and
scene access; the earlier report's version and status are not a substitute
for checking this session. The prior addon-status error did not prevent
scene operations; investigate a current error only if it blocks a needed
operation. Do not reinstall a working connection to repair unrelated status
reporting.

Work in short, observable passes. For each meaningful change:
1. Record the specific visible problem and its likely layer.
2. Inspect enough scene evidence to test that explanation.
3. Make a focused, reversible change.
4. Capture and inspect the same view before and after.
5. Accept, revise, or roll back based on evidence.

Save checkpoints before changes to topology, UVs, facial geometry, or
texture baking. Reuse task-owned objects when resuming; avoid duplicate
eyes, smiles, scars, cameras, or garment shells accumulating across attempts.

PASS 0 — RECOVER THE REAL BASELINE

[ ] Verify the remote .blend exists and identify the iteration-1 working
    scene, source scene, and GLB verification scene. The report names the
    working scene 3dobject1_Work; confirm rather than relying on the name.
[ ] Identify the character meshes, current material assignments, semantic
    face attributes, UVs, packed images, added facial objects, and cameras.
    The previous report states 21 exported meshes and two 2048px textures;
    record actual values and explain important discrepancies.
[ ] Duplicate the working scene with independent data where edits require
    it, and save iteration2/checkpoints/baseline.blend. Preserve the prior
    project and source copy. Hide irrelevant verification/source duplicates
    from refinement renders and exports.
[ ] Capture a front, side, back, face, torso, and hand/feet baseline with the
    actual resumed model. Check that it corresponds to the supplied evidence.
[ ] Verify the stored camera, lighting, and color-management settings.
    Record them so that later visual changes can be attributed correctly.

Output: a recoverable current baseline and a prioritized issue ledger.
Do not reset to white_mesh.glb or repeat the first import/coloring workflow.

PASS 1 — MAKE THE COMPARISON RELIABLE

The goal is a close portrait full-body image. The local iteration-1 evidence
is landscape viewport capture; the report says native portrait renders also
exist remotely. Inspect a native saved render when the tool permits. Keep
these two kinds of evidence distinguished.

Create a named iteration-2 comparison camera and preserve the old one.
Fit the goal's framing, elevation, orientation, perspective, and visible
foreshortening. The previous camera was reported orthographic; test whether
a perspective camera better explains the reference before retaining it.
Do not change the mesh to compensate for a framing mismatch.

Use a portrait review render of at least 1024 x 1536 when practical. Frame
the entire hat and sandals with comparable margins. Crop comparison copies
consistently and normalize by character height; do not stretch either image
or independently zoom each body part until it seems similar.

Inspect landmark ratios and positions: hat width, crown/brim proportions,
face width, eyes and mouth, shoulders, fist relative to torso, waistband,
sash end, cuff heights, and feet. Record the important differences that
remain after camera alignment. Treat single-view hidden detail as unknown.

Once aligned, keep the new comparison camera, exposure, and review lighting
stable during geometry and boundary work. Use additional inspection views
for profile and details. Any later camera change needs a stated reason.

Acceptance: the goal and current result are meaningfully comparable, and
proportion corrections are based on that comparison rather than screenshots
with different framing.

PASS 2 — DIAGNOSE AND REPAIR REGION BOUNDARIES

Inspect the visible problem areas first:
- Jagged red/skin edges at the neck, collar, and shoulder line.
- The abrupt sides of the exposed chest opening.
- Lower jacket hem, sash, and shorts transitions.
- The lowered hand where it meets the shorts.
- Sleeve openings beside the forward fist and lowered wrist.
- Dark irregularities around the rear hat/hair contact.

For each area, distinguish the causes rather than applying one broad fix:
1. Inspect the relevant face labels/material indices and UV islands.
2. Check the region using simple contrasting debug materials or masks.
3. Inspect the underlying surface in neutral shading and wireframe.
4. Temporarily disable detailed normal/roughness textures to isolate their
   effect; restore them after the diagnostic.
5. Inspect the actual base-color pixels and texture filtering at the boundary.
6. Check whether the image being displayed, saved, packed, and exported is
   the same current image, especially after UV or atlas revisions.

Possible causes include incorrect semantic selection, a coarse color mask,
texture bleed, UV distortion, a cut across garment geometry, or an actual
mesh intersection. Confirm the cause on the real asset before choosing a
repair. Raising texture resolution alone does not correct a wrong boundary.

Correct region labels and paint/masks along the actual garment outline.
Create or refine a physical garment edge where the outline needs depth.
Use enough local topology for smooth boundaries without subdividing the
whole figure indiscriminately. Inspect front, oblique, and profile views.

Acceptance: no obvious red triangles intrude on the neck/skin; the jacket
opening and sleeve-to-hand edges are clean; hand, sash, and shorts remain
separate; the back hat artifact is identified and corrected or documented
with a specific unresolved cause.

PASS 3 — INTEGRATE THE FACE

The current eyes and smile are visibly too applied-piece-like compared
with the goal. Diagnose their geometry, depth, placement, and shading on
the current scene, using both the face close-up and side view.

Eyes and expression:
- Match the visible eye outline and pupil placement from the goal after
  camera alignment. Check each eye independently rather than enforcing an
  unsuitable mirror across an asymmetrically viewed face.
- Use gently curved, fitted eye surfaces integrated with shallow sockets
  and eyelid/lid-border forms. Keep the intended stylized large eyes, but
  reduce conspicuous protrusion. Avoid a protruding sphere or white disc
  simply sitting above the cheek surface.
- Keep pupils fitted to those surfaces, with coherent depth and restrained
  highlights. Check for floating pupils, clipping, hair intersection, and
  a side-visible gap behind the eye.
- Refine eyebrows, brow attitude, surrounding skin, and hairline where
  necessary to recover the target's expressive face. Avoid a permanent
  surprised stare when the reference is more confident and focused.

Smile and facial form:
- Make the grin follow the curvature of the face, with a shallow mouth
  opening, integrated lip/cheek transitions, and a curved pale tooth surface.
- Match the goal's smile width, height, arc, and thickness. The current
  narrow outlined crescent must not remain the only mouth construction.
- Avoid a thick black drawn border, floating teeth ribbon, flat pasted smile,
  or exaggerated individually separated teeth unsupported by the reference.
- Preserve and refine the nose, cheeks, chin, and expression. Do not solve
  the eyes while leaving the mouth or profile integration visibly worse.

Cheek scar:
- Keep the stitched mark in the goal's image-right cheek region.
- Follow the cheek surface, with small, controlled marks and subtle depth.
  Ensure the stitches do not float, cross an eyelid, or dominate the face.

Use the technique appropriate to the actual defect: repositioning and
reshaping existing detail objects, local sculpting or topology refinement,
or replacing a poor added detail on the working copy. A broad decal is not
an adequate replacement for necessary facial volume.

Acceptance: matched-view and side face images show eyes integrated into the
head, a volumetric grin following the face, no obvious detail-object gaps,
and a materially improved expression. Save a face checkpoint.

PASS 4 — TORSO, SCAR, HANDS, FEET, AND SANDALS

Torso:
- Refine the visible chest, abdomen, and transition into the sash to match
  the goal's sculpted volume: pectoral forms, segmented abdominal forms,
  central contour, and appropriate transitions into the shoulders.
- Use broad anatomical form first. Do not approximate abdominal muscles
  with dark stripes, random bumps, isolated spheres, or pasted shading.
- Keep the anatomy stylized and proportional. Use local refinement and
  inspect silhouette and oblique lighting before accepting the result.

Chest scar:
- The current thin straight X is not enough. Match the reference's wider,
  irregular reddish-brown scar shape and its placement across the upper torso.
- Follow torso curvature and add restrained scar edge/relief where needed.
  Integrate it with skin; avoid ruler-straight strokes, floating crossed
  strips, or deep cuts that change the intended expression of the asset.

Forward fist and lower hand:
- Keep their pose and placement. Refine identifiable knuckles, fingers,
  finger separations/creases, thumb, and wrist transition.
- The forward fist must stop reading as an undifferentiated block. Use
  reference-view and oblique hand close-ups to judge articulation.
- Do not lengthen fingers or change foreshortening blindly; verify camera
  and local shape first. Preserve plausible hand anatomy and skin boundaries.

Feet and sandals:
- Improve toes, ankle transitions, and the visible foot/sole separation.
- Make black straps read as fitted straps with width and thickness, not
  thin wavy lines painted on top of an indistinct foot.
- Fit strap contacts to the foot; check their front and side profiles.
- Keep soles tan and give their thickness and straw-like surface a coherent
  shape. Avoid foot intersections or straps floating above the skin.

Use actual geometry for visible silhouette, contact, and large form.
Normal/bump detail can support small surface detail but must not stand in
for missing knuckles, lips, cuff volume, or garment thickness.

Acceptance: torso and scar resemble the reference's forms, hands and feet
are visibly articulated, and sandals survive close-up/profile inspection.

PASS 5 — CLOTHING AND SASH STRUCTURE

Jacket:
- Refine the open front and collar/lapel transitions into actual garment
  edges with readable thickness where the reference shows it.
- Match major folds and cloth tension around the shoulders, elbows, sleeve
  ends, chest edges, and flared hem. Keep existing good folds; add local
  structure where the source is visibly too simple.
- Preserve the exposed torso and sleeve silhouette. Avoid a second jacket
  shell intersecting the first, or a rigid red painted torso surface.
- Refine button rims and highlights so the visible golden/yellow buttons
  have a clear surface and fit the jacket edge. Keep their reference placement.

Shorts and cuffs:
- Refine waistband, center seam, major leg folds, and transitions to the
  cuffs as needed. Maintain the blue shorts and their pose.
- Replace the uniformly smooth white cuff appearance with the reference's
  thick, irregular rolled/frayed trim. Vary the trim shape and detail in a
  controlled direction, fitted to the leg opening.
- Use real cuff volume for visible contour, then fine texture/normal detail.
  Avoid rows of identical beads, random noisy blobs, or long fur strands
  that change the style of the goal.

Sash:
- Make the waist wrap read as layers of yellow fabric rather than a flat
  rectangular color panel. Refine folds, edge transitions, and waist contact.
- Inspect the image-right knot and tail from front and side. Match the
  broad trailing shape and drape; replace visibly tube/ring-like or overly
  simplified local construction with coherent folded cloth where necessary.
- Preserve the intended tail location and overall pose. Avoid increasing
  its volume until it obscures the jacket, shorts, or hand.

For fitted additions, inspect surface offsets and thickness. Choose local
mesh fitting/sculpting or suitable modifiers based on the asset. Check all
additions for clipping, self-intersection, Z-fighting, and floating gaps.
Keep the result static; cloth simulation is optional only if justified by
an identified need, not a substitute for shaping the visible reference.

Acceptance: garment boundaries look intentional, jacket and cuffs have
appropriate depth, and the sash looks like wrapped and knotted fabric in
both the comparison and inspection views.

PASS 6 — HAT, HAIR, AND SURFACE CHARACTER

Hat:
- Compare crown shape, brim width, brim curvature and thickness, and red
  band height/placement after alignment. Make evidenced local corrections.
- The current uniform fine pattern does not yet read like the goal's woven
  straw. Build directional structure at two scales: readable interwoven or
  braided bundles, then smaller fiber detail. Follow the crown and brim's
  actual form rather than using a uniform checker or generic noise.
- Use local geometry where strands materially affect the silhouette or
  close-up relief; use texture/normal detail for finer fibers. Avoid dense
  floating strand spaghetti or excessive geometry with no visible benefit.
- Make the red band a clean fabric feature with consistent boundaries.
  Inspect its back and the underside where hair approaches the brim.
- Diagnose the dark back/hat irregularity before correcting it: material
  leakage, intersection, incomplete underside, or shading can look similar.

Hair:
- Retain useful existing locks and their shape. Improve coherence and
  restrained strand highlights; avoid an excessively shiny spiky plastic look.
- Correct hair/hat and hair/skin intersections and misplaced dark regions.
  Add detail only where it improves the image rather than obscuring the face.

Cloth and skin:
- Give red jacket, blue shorts, and yellow sash their distinct fabric
  response and properly scaled, directional weave. Large folds come from
  modeled form; fine weave should support those forms rather than dominate.
- Keep skin warm and softly shaded with subtle variation. Separate render
  noise from actual skin texture before introducing or removing detail.
- Tune materials under the fixed comparison conditions. Do not globally
  increase saturation or roughness to compensate for unrelated geometry.

If procedural textures or detailed sculpting need baking for GLB, prepare
compatible image maps after topology and UVs are stable. Check the actual
installed Blender exporter and material setup rather than assuming every
Blender shader feature will survive export.

Acceptance: the hat reads as directional straw, the band has clean fabric
edges, hair remains distinct, and cloth detail is visible at the appropriate
scale without introducing new noise or boundary defects.

PASS 7 — REVIEW REAL VISUAL IMPROVEMENT

Render a comparable portrait view, face, chest/clothing, hands/feet, side,
and back. Use soft neutral studio lighting, a pale-gray background/floor,
and contact shadows close to the goal. Keep the whole figure visible.

Make a goal / iteration-1 / iteration-2 comparison at consistent framing.
If the old native render is available remotely, use it. If only a viewport
capture is locally available, label the comparison limitation and normalize
its framing without claiming identical render conditions.

For each major priority in this brief, state:
- What visibly changed.
- Which before/after view demonstrates it.
- Whether it is resolved, improved but partial, or still unresolved.
- The next action for any remaining important gap.

Review the three largest remaining discrepancies and correct actionable
ones before finalizing. Avoid endless blind tweaking. Check that a local
improvement did not introduce clipping, warped texture, lost pose, duplicate
details, or new artifacts elsewhere. Do not hide defects with distance,
cropping, blur, dramatic light, or a changed camera.

No invented similarity percentage. No acceptance solely because the model
has the right colors, a file exists, or an agent feels confident.

PASS 8 — SAVE AND REGRESSION-CHECK DELIVERY

Create these new remote iteration-2 artifacts:
- final/luffy_refined.blend
- final/luffy_refined.glb
- renders/preview_match.png
- renders/detail_face.png
- renders/detail_torso_clothing.png
- renders/detail_hands_feet.png
- renders/preview_side.png
- renders/preview_back.png
- renders/roundtrip_match.png
- verification.md and the single current task ledger/selected plan
- Checkpoints and texture assets needed to recover the work

Do not overwrite iteration-1 final files. Save and inspect the editable
project with current textures. After UV or texture revisions, check current
image pixels, saved files, packed images, and exported images for stale data.
The previous iteration had a real stale packed-image problem; make this a
targeted regression check instead of repeating the whole exporter workflow
without a reason.

Export only the intended refined character. The object count may change
legitimately with refinements; do not force the previous count of 21.
Exclude source copies, baseline scenes, floor, lights, and helpers unless
they are deliberately part of the model deliverable.

Reimport the new GLB into an isolated verification scene. Check actual
geometry, visible materials, UVs, texture/normal detail, orientation, scale,
and absence of unwanted objects. Inspect a round-trip render under matched
settings. Update normal maps after geometry/UV changes when required.

Where artifact delivery is supported, place new review images and reports
in the local iteration2/ folder. Where it is not supported, clearly list
the remote artifacts and provide available MCP viewport captures locally.
Never claim that remote model/native render files were delivered locally
when only path strings or screenshots are available.

ITERATION-2 ACCEPTANCE AND RETURN

[ ] Prior source, iteration-1 artifacts, and original local inputs preserved.
[ ] Actual latest remote project resumed; no reset to uncolored source.
[ ] Comparable portrait framing established and kept stable for review.
[ ] Face integration improved in both front close-up and profile.
[ ] Collar, chest, sleeves, hand/shorts contact, sash, and back-hat defects
    diagnosed and visibly repaired or specifically documented as unresolved.
[ ] Torso and scar have appropriate reference-like volume and shape.
[ ] Hands, feet, and sandals show clear anatomical/contact improvements.
[ ] Cuffs, sash, jacket edges, and hat straw materially improved.
[ ] Before/after views demonstrate improvement rather than just new claims.
[ ] New .blend saved and checked; GLB reimported and visually inspected.
[ ] Texture packing/export regression checked after any relevant changes.
[ ] Local delivery distinguished from remote-only artifacts.

Return the artifact paths, comparison views, and verification report to the
Director. List actual changes, review evidence, failed/unverified checks,
remaining differences, and a concrete next corrective action. Mark the
overall visual result partial if important gaps remain, even when technical
export checks pass. Keep working through actionable refinements within the
assignment rather than stopping after a cosmetic material adjustment.

This assignment is a refinement pass, not a promise that one photograph
uniquely determines a perfect 3D object. Preserve plausible side/back
surfaces and disclose assumptions. Do not claim print readiness, watertight
production geometry, or validation in external viewers unless actually
checked. Do not edit repository instructions or install integrations.
```

## Director acceptance rationale

The next return should establish **visible improvement over iteration 1**, particularly in face integration, garment boundaries, torso/hand detail, and the hat/cuffs/sash. File saving and GLB round-trip checks remain necessary regression checks, but they cannot replace this visual review.

The Director should request corrections if those priorities are unchanged, if the agent restarts and loses the current work, or if a report labels obvious visual defects as fully accepted without evidence. Partial progress with clear evidence and a concrete blocker is more useful than a blanket completion claim.

## Technical references for the executing specialist

- [Blender Shrinkwrap documentation](https://docs.blender.org/manual/en/5.1/modeling/modifiers/deform/shrinkwrap.html): fitting selected local detail geometry and managing offsets.
- [Blender render baking documentation](https://docs.staging.blender.org/manual/en/latest/render/cycles/baking.html): baking detail and procedural appearances into image maps where appropriate.
- [glTF 2.0 specification](https://github.com/KhronosGroup/glTF/blob/main/specification/2.0/Specification.adoc): material and normal-texture representation for export verification.

Primary documentation search results informed the implementation guidance; full Blender manual retrieval was unavailable. The specialist must verify version-specific APIs and exporter behavior against its installed Blender. These references are not evidence that any iteration-2 modeling or export has already been executed.
