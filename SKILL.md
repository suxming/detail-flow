---
name: detail-flow
description: Build, redesign, polish, or review product detail pages for products, AI tools, models, SaaS features, developer products, plugins, ecommerce listings, and technical showcases. Use when the user provides a product image, reference image, screenshot, product concept, or existing page and asks for a detail page, ecommerce detail page, 10-, 12-, 14-, or 16-screen product page, long-form sales page, model page, product feature page, visual polish, responsive frontend implementation, screenshot-based QA, or reusable workflow derived from an existing product page project.
---

# DetailFlow

## Overview

Use this skill to turn a product or feature idea into a useful, polished detail page. Prioritize clear product communication, real user workflows, implementation quality, responsive behavior, and visual assets that reveal the product rather than decorative filler. Keep the skill general-purpose: it may be used with different image-generation tools, frontend stacks, or local pipelines, but its core job is product detail-page planning, generation, review, and iteration.

## Execution Contract

For image-led ecommerce detail-page requests, follow the defined DetailFlow route strictly. Treat this contract as higher priority than convenience, improvisation, or tool preference.

- MUST resolve the page specification before writing the blueprint. Default to `10` screens and exact `800 × 1200 px` (`2:3`) slices. If the user explicitly requests an extended supported format, allow `12`, `14`, or `16` screens and/or exact `1080 × 1920 px` (`9:16`) slices. Do not silently select an extended format. For any other screen count, pixel size, or ratio, ask the user to choose a supported format before generation.
- MUST follow this order: analyze inputs -> resolve the page specification -> produce the page blueprint -> wait for blueprint approval -> establish the text and visual masters -> generate and internally inspect a 1:3 continuous visual master covering the complete planned page (screens 01 through the selected final screen) -> generate exactly 2 final slices -> create and internally inspect their 2-slice concatenated preview -> present the complete-page master, both slices, preview, and audit together at the first visual approval gate -> wait for explicit user confirmation -> revise only the responsible master or batch until the user confirms no further changes are needed -> generate the next 2 slices -> repeat the 2-slice confirmation cycle until all slices are approved -> run the final audit -> save and report the output folder.
- MUST use the selected exact canvas for every final ecommerce detail-page slice: default `800 × 1200 px` (`2:3`), or user-requested `1080 × 1920 px` (`9:16`). Verify every final slice's pixel dimensions before presentation and delivery. Keep one canvas specification for the complete set unless the user explicitly restarts planning with a different supported format.
- MUST generate the complete-page 1:3 visual master whenever producing the first `01-02` batch for an image-led ecommerce long page. The master must preview the visual narrative for all planned screens, not only screens 01-02. Do not present screens 01-02 for approval without also presenting this master unless the user explicitly declines a master or the image-generation capability cannot create one.
- MUST use progressive 2-slice approval gates. Approval 1 confirms the complete page blueprint. Every later gate confirms exactly one newly generated 2-slice batch and its concatenated preview. Continue with `01-02`, `03-04`, `05-06`, and so on through the selected final screen. All supported totals are even, so every visual batch contains exactly 2 slices.
- MUST stop after presenting every 2-slice batch. Do not generate any later slice until the user explicitly confirms that the current batch needs no further modification. Treat revision requests as approval withheld: revise only the affected slice or batch, present the revised batch and preview again, and wait for confirmation.
- MUST NOT interpret silence, an earlier approval, or approval of only one item as permission to continue. A generic request such as "continue" counts only when the current batch has already been presented and no unresolved revision request remains.
- MUST inspect every generated master and staged output before continuing. Do not proceed when the image is textless despite planned copy, reads as unrelated standalone posters, ignores the reference style, changes the product, contains garbled text, or invents unsupported claims.
- MUST use the user's product images, reference images, confirmed facts, approved blueprint, and approved masters as the authoritative inputs. Do not replace them with a newly invented concept or a generic category template.
- MUST keep the task scoped to the requested ecommerce image set. Do not create a website, video, animation, presentation, application, workflow node, Python script, automation script, or other auxiliary artifact unless the user explicitly asks for that artifact.
- MUST NOT write code merely to simulate image generation, create placeholder deliverables, or bypass an unavailable image-generation/editing capability. If a required capability is unavailable or fails, state the limitation and stop at the current stage or offer the smallest relevant alternative.
- MUST keep the requested deliverable scope stable: do not add unrelated stages, output formats, image counts, or auxiliary deliverables without approval. When the user provides limited product information, infer suitable selling-point copy, scene ideas, visual motifs, labels, and supporting content from the product images, product category, reference images, and common buyer concerns. Clearly distinguish reasonable creative inference from confirmed facts. Do not invent exact technical parameters, certifications, awards, medical effects, discounts, or brand partnerships that are not supported by the user or source material.
- MUST NOT silently change the production route after a failed result. Revise only the smallest responsible layer described in the revision-routing rules, then request confirmation when the change affects an approved blueprint or master.
- MUST preserve approved outputs. Do not overwrite or discard accepted masters or slices while experimenting; save revisions as clearly identified replacements or versions.
- MAY use lightweight existing utilities only when they are necessary for deterministic operations such as reading image dimensions, concatenating approved slices, checking files, or saving deliverables. Do not create new utility scripts for these operations unless the user explicitly requests automation.

If the user's request is ambiguous, choose the narrowest action that advances the current DetailFlow stage. Ask before expanding scope.

## Core Workflow

For image-to-ecommerce detail page requests, do not generate final images immediately. First produce a structured page blueprint and ask the user to confirm or revise it. Generate images only after the user approves the content plan, unless the user explicitly asks to skip planning.

1. Clarify the product surface

   Identify the product name, audience, primary promise, concrete capabilities, constraints, proof points, and expected call to action. If the user provides a product image or reference image, infer visible materials, form, style, category, likely buyer concerns, and differentiators before writing page sections. If the user provides an existing page, inspect the current structure before proposing changes.

2. Shape the page architecture

   Build a scannable narrative: first-viewport identity, practical value, capability sections, examples or use cases, trust/proof, limits or requirements when relevant, and a clear next action. For ecommerce long pages, split the story into deliberate screens with one main job per screen, but vary the information weight across screens. Not every screen needs a campaign-style headline and subtitle; some screens should use smaller guide copy, explanatory paragraphs, labels, badges, callouts, ingredient/detail notes, comparisons, or scene captions. Avoid generic marketing copy that could describe any product.

   For image-led ecommerce long pages, make the first screen establish 2-4 core claim seeds. Later screens should unpack, prove, visualize, or contextualize those seeds instead of introducing unrelated new selling points. If a later screen's copy cannot be traced back to a first-screen seed, revise either the first-screen seed set or the later screen's job.

3. Match the existing project

   Read the repository structure, framework, routing, component conventions, design tokens, asset strategy, and local styling patterns before editing. Reuse existing components and utilities when they fit.

4. Design for product comprehension

   Make the product itself a first-viewport signal. Use screenshots, generated visuals, product mockups, demos, or domain-relevant imagery when appropriate. Keep operational tools dense, restrained, and easy to scan; use more expressive visuals only when the product category supports it.

5. Implement the page

   Edit the smallest reasonable set of files. Keep content, layout, and interaction states complete enough that the page feels like a real product surface, not a placeholder. Respect existing frontend guidance for accessibility, responsiveness, and visual hierarchy.

6. Verify with real rendering

   Start the app when needed. Check desktop and mobile viewports with screenshots or browser inspection. Fix text overflow, overlapping elements, blank media, awkward crop/framing, one-note color palettes, missing states, and layout shifts before handing off.

## Image Generation Workflow

Use this workflow when the user provides a product image and asks for an ecommerce detail page, a supported 10-, 12-, 14-, or 16-screen page, long sales image, or style-reference-based product page.

1. Analyze inputs

   Describe the product image and reference style separately. List observed product facts, inferred selling points, and unknowns that should not be invented.

   Before writing the blueprint, give the user one concise opportunity to provide confirmed selling points, specifications, functions, audience, or prohibited claims when these are not already supplied. Do not make this a mandatory questionnaire. If the user chooses not to add information, continue using product-image evidence and reasonable category-level inference, and clearly state that unconfirmed selling points are AI-inferred and should be reviewed before commercial use.

   When a reference image contains a strong character, model, mascot, hand, prop, or scene language, treat it as part of the reference style DNA if it supports the user's requested style. Preserve the visual language at an abstract level, such as 3D cartoon character presence, friendly brand host, hand-held product reveal, low-angle lifestyle shot, or macro annotation style. Do not copy the reference image's original brand, exact person identity, text, or product.

2. Produce the page blueprint first

   Output a page blueprint for the selected total before generating images: default 10 screens, or user-requested 12, 14, or 16 screens. Record the selected `screen_count`, `slice_width_px`, `slice_height_px`, and `slice_ratio` once at the top of the blueprint. The blueprint must include these fields for each screen: `slice_id`, `buyer_question`, `module_type`, `module_label`, `claim_seed`, `screen_job`, `evidence_type`, `claim_visual_evidence`, `evidence_visibility`, `unsupported_visual_claims`, `content_density`, `layout_archetype`, `copy_module_type`, `copy_structure_pattern`, `primary_module`, `secondary_modules`, `text_exact`, `hierarchy_strategy`, `composition_shift`, `transition_type`, `edge_zone_percent`, `top_edge_anchor`, `bottom_edge_anchor`, `allowed_edge_elements`, `forbidden_edge_elements`, `previous_edge_reference`, `seam_audit_rule`, `visual_composition`, `reference_style_notes`, and `risk_unknowns`. Ask the user to confirm or revise the blueprint before generating images.

   First define the screen-01 `claim_seed` set before writing later screens. Use 2-4 short seeds such as visible ingredient/detail, texture promise, usage moment, trust cue, convenience, or emotional hook. Each later screen must name the seed it is expanding. Do not introduce a later-screen selling point that was not seeded on screen 01 unless the user explicitly asks for a new chapter.

   Treat these fields as planning controls, not visible labels. Do not write internal labels such as `module_type`, `detail`, `parameter_trust`, `FAQ`, or `screen_job` into visible page copy. Convert them into natural buyer-facing Chinese copy.

   Do not force every screen into the same `headline + subtitle` structure. Reserve the strongest headline/subtitle treatment for the first screen or other true section openers. Later screens should choose copy modules based on the section's job: explanatory text, small guide title, label clusters, icon notes, proof callouts, ingredient/detail annotations, scenario captions, comparison rows, trust bullets, or closing CTA. The copy structure should drive layout variation and hierarchy.

   Assign a distinct `copy_structure_pattern` to each screen or at least avoid repeating the same pattern in adjacent screens. Examples: `hero_claim_stack`, `question_answer`, `single_line_with_labels`, `annotation_map`, `three_point_breakdown`, `scene_caption_cluster`, `mini_steps`, `trust_checklist`, `quiet_closing`. Different patterns should change sentence rhythm, visible text keys, line count, and layout behavior, not just rename the same headline/body structure.

   Before asking for approval, audit copy differentiation, seed continuity, and copy structure variety. Each screen must answer a different buyer question and carry a distinct copy role, while still tracing back to the first-screen claim seeds. If adjacent screens are interchangeable when read without images, rewrite the plan. If a later screen feels like a new standalone topic rather than a deeper explanation of a seeded claim, rewrite it. If three or more screens share the same sentence rhythm, such as `headline + one explanatory sentence + three tags`, rewrite their `copy_structure_pattern`. Do not let every screen repeat the same taste, quality, convenience, or emotional promise with minor wording changes.

   At least 70% of screens should have 2-4 content points through one `primary_module` plus 1-3 `secondary_modules`, unless the user's format requires an intentionally sparse visual. Low-density screens may use fewer words, but they still need a clear role such as transition, scene atmosphere, trust note, product identity, or closing emotion.

### Claim-to-Visual Evidence Contract

Treat every visible selling point as a claim that requires matching visual evidence in the same slice.

- MUST make the screen's headline, labels, annotations, and supporting copy match what the generated image visibly shows. A selling point and its evidence must appear in the same slice unless the copy explicitly refers to another confirmed source.
- MUST define `claim_visual_evidence` before generation. Map every visible claim in `text_exact` to the exact product part, action, scene, comparison, parameter graphic, or source note that will support it.
- MUST define `evidence_visibility` as `direct`, `contextual`, or `source_only` for every claim:
  - `direct`: the screen visibly shows the claimed product part, material, action, quantity relationship, or supplied parameter.
  - `contextual`: the screen illustrates a usage situation or emotional benefit but does not prove technical performance. Keep the copy experiential and non-technical.
  - `source_only`: the claim comes from the user's supplied product information or reference material and cannot be proven visually. Display it as a factual parameter with a clear source or qualification; do not fake visual proof.
- MUST define `unsupported_visual_claims`: claims the planned image cannot honestly support. Remove them from visible copy or change the visual plan before generation.
- MUST NOT use generic lifestyle imagery as proof of technical performance. A family scene cannot prove capacity, insulation duration, safety, leak resistance, material grade, durability, or ease of cleaning.
- MUST NOT use decorative icons, fake cutaways, simulated measurements, steam, water flow, smiling people, or before/after imagery as technical evidence unless the underlying claim is confirmed and the visual honestly represents it.
- For capacity claims, show a confirmed parameter label or an honest scale/usage relationship without inventing exact cup counts.
- For material claims, show the relevant confirmed product part or a material macro and include the supplied material label. Do not infer certifications or performance properties from appearance.
- For insulation or duration claims, use the supplied parameter with a source/condition note. Time-of-day scenes may illustrate use context but are not proof of measured performance.
- For handling or pouring claims, show the actual visible handle, spout, grip, and pouring action. Keep copy limited to observable structure or action; do not infer anti-drip, anti-scald, leak-proof, effort reduction, or ergonomic test results.
- For emotional or lifestyle claims, use a matching scene and write experiential copy rather than technical proof language.
- Before generating a slice, run a claim-evidence check. If any visible claim lacks a mapped visual or source note, revise `text_exact` or the visual composition first.
- After generation, fail the slice when the promised evidence is missing, too small to understand, visually contradictory, replaced by a different product part, or unable to support the visible copy. Regenerate only that slice or repair its copy area.

3. Lock the long-scroll masters and structure before final slice generation

   Create or confirm the long-scroll masters and structure before generating final screens:

   - Text master: `visual_master_spec`, `master_reference_prompt`, and `visual_style_dna`. Use it to lock palette, lighting, space, materials, typography, continuity motifs, reference-style DNA, product identity rules, section rhythm, information density, and page structure.
   - Image master: a 1:3 continuous long-page master reference covering the complete approved page plan, from screen 01 through the selected final screen. Generate it before or alongside the first `01-02` final batch and present all three at the same first visual approval gate. Use it to lock the full-page visual narrative and spatial continuity: background world, floor/table perspective, light direction, ingredient/particle flow, recurring visual motifs, product scale rhythm, section-to-section transitions, and the overall visible copy hierarchy. The master must contain the selected number of legible compositional regions or a clearly mappable rhythm corresponding to the approved blueprint, including future screens that have not yet been rendered as final slices. Include simplified visible Chinese copy or clearly reserved text modules that reflect the approved `text_exact` hierarchy; do not make a completely textless master unless the user explicitly asks for a pure spatial reference.
   - Structure blueprint: ordered screen items using `module_type`, `claim_seed`, `screen_job`, `evidence_type`, `content_density`, `primary_module`, `secondary_modules`, `text_exact`, `hierarchy_strategy`, `composition_shift`, and edge anchors. Use it as the highest priority source for final prompts.

   The 1:3 image master is a required reference artifact for the first `01-02` batch, not a crop source and not a replacement for the approved slice canvas. It previews the complete selected screen range as one continuous visual system so the user can judge the later-page direction before approving the first two final screens. Do not copy it pixel-for-pixel, crop it into final images, or force every slice to match its exact composition. If the 1:3 master covers only screens 01-02, cannot be mapped to the complete blueprint, looks like independent posters instead of one continuous ecommerce detail page, lacks the expected text hierarchy, or repeats the same product/character/primary-motif hero composition across many regions, revise the master before presenting the first batch.

4. Generate final page sections

   Generate final screens as sequential long-scroll detail-page slices. Use the page specification approved with the blueprint: default exact `800 × 1200 px` (`2:3`), or user-requested exact `1080 × 1920 px` (`9:16`). Each slice must follow the approved blueprint exactly: do not change `module_type`, `screen_job`, `evidence_type`, `claim_visual_evidence`, `evidence_visibility`, `content_density`, `primary_module`, `secondary_modules`, or `text_exact` during prompt writing. Each slice must carry 2-4 content points when appropriate, with one primary module plus secondary modules from the approved structure. Do not simplify every slice into a single poster headline and hero image.

   When a 1:3 spatial master exists, each final slice prompt should state the selected exact canvas and reference the master as the shared spatial continuity anchor: inherit its background world, lighting direction, material atmosphere, product scale rhythm, recurring motifs, ingredient or prop flow, and transition logic while expanding the current slice's own structure. State explicitly that the slice should feel like a detailed expansion of one region of the same long-scroll page system, not a standalone poster.

   Generate final slices in batches of exactly 2. For the first batch, generate the complete continuous 1:3 visual master for the selected screen range and screens 01-02 as one coordinated milestone. Concatenate screens 01-02 into a two-screen preview, inspect the master, both slices, and their seam, then present: (1) the complete-page master, (2) screen 01, (3) screen 02, (4) the 01-02 concatenated preview, and (5) a concise audit. Ask the user to approve both the complete-page direction and the detailed 01-02 execution. For every later batch, concatenate the two new slices into a batch preview and inspect it before presentation. Also concatenate the first slice of the batch with its immediate predecessor and inspect that boundary. Present both individual slices, the batch preview, and a concise audit, then stop for explicit user confirmation. If the user requests changes, revise only the affected master, slice, or batch, rebuild the relevant previews, present them again, and continue waiting. Generate the next 2-slice batch only after the user confirms that the current batch needs no further modification. Continue until the selected final screen. Do not defer seam inspection until the full set is complete. If a batch or adjacent seam fails internally, revise the smallest affected neighboring slice range before presentation; return to the blueprint only when the approved narrative itself is responsible.

5. Prepare split delivery or long-image concat

   If the user wants separate images, deliver them as sequential page slices from the same long-scroll system. If the user wants a long image, concatenate the slices in order. Keep shared backgrounds, lighting, product identity, recurring visual motifs, typography system, spacing rhythm, and transitions consistent. Do not make each section a standalone social poster unless the user explicitly asks for poster-style outputs. Keep product identity consistent across the set and avoid changing visible product color, shape, brand marks, or distinctive components.

   Do not rely on text-only "continue from previous slice" instructions when generating independent images one by one. A slice generated without previous/next visual context will usually reset into a complete standalone composition. For true continuity, use the project long-scroll pipeline when available: create the structure blueprint, build prompts with the selected exact canvas, generate ordered slices with explicit edge anchors, concatenate a preview, then revise slices whose top/bottom edges fail to connect. If the generation tool supports image references or outpainting, use the previous slice bottom and next slice plan as visual context for the current slice.

### Edge Continuity Contract

Treat adjacent-slice continuity as a deterministic production constraint, not a vague style suggestion.

- MUST prioritize full-bleed composition over visible blank transition bands. Fill each slice with meaningful photography, color fields, texture, panels, or other designed content whenever this can be done without product distortion or awkward cropping.
- MUST use this transition priority: (1) verified visual continuation when actual edge context is available, (2) full-bleed scene-to-scene or section-to-section transition, (3) restrained whitespace only when full-bleed treatment would deform the product, damage product identity, create a bad crop, or materially weaken the composition.
- MUST preserve product identity over full-bleed coverage. Never stretch, widen, compress, over-enlarge, redraw, or alter the product's proportions, orientation, color, logo, handle, spout, controls, or distinctive components merely to fill the frame. If full-bleed placement would cause product drift, reduce the product scale or introduce controlled whitespace around the product while keeping the rest of the slice visually designed.
- MUST NOT render transition-safe zones as automatic empty strips. Treat them as content-protection zones, not mandatory visible whitespace. Background photography, wall color, wood tone, texture, gradients, light, shadow, and noncritical designed content may fill them edge to edge.
- For independently generated images, do not continue identifiable objects across slices unless actual edge context is supplied. Continue color, lighting, texture, shadow direction, simple lines, gradients, or other abstract visual material; otherwise end one full-bleed section cleanly and start the next full-bleed section immediately.
- Reserve the top 8-12% and bottom 8-12% of every slice as transition-safe content zones. Record the chosen percentage in `edge_zone_percent`; this percentage protects critical content and does not prescribe blank space.
- Keep headlines, parameters, product proof, faces, hands, logos, complete products, and other critical content out of transition-safe zones.
- Do not repeat or recreate cups, fruit, products, hands, people, furniture edges, tabletops, cards, props, or text from the neighboring slice inside an edge zone.
- Never ask the next slice to redraw the previous slice's bottom objects. Redrawing produces duplicated tables, cups, products, bands, and false continuity.
- Prefer continuity through background color, full-bleed wall or floor fields, soft light, shadow direction, paper or wall texture, wood tone, thin rules, gradients, steam curves, or ribbons.
- When exact object continuation is unavailable, use a full-bleed section boundary such as an immediate scene cut, soft color field, thin divider, rounded panel edge, or full-width background change. Use clean whitespace only after confirming that full-bleed treatment would distort the product or make the composition worse. A controlled full-screen section break is better than fake seamless continuity or a large automatic blank band.
- Use identifiable-object continuation only when the generation tool receives the actual previous bottom-edge crop as visual context or supports outpainting. Extend from the supplied edge; do not recreate it from text.
- Keep `bottom_edge_anchor` of slice N compatible with `top_edge_anchor` of slice N+1. They must describe the same transition type, palette, position, width, and direction.

Every adjacent pair must choose exactly one `transition_type`:

1. `clean_section_break`: use an immediate full-bleed scene cut, a thin rule, a rounded panel boundary, or a controlled full-width background change. Use whitespace only as the product-preserving fallback, not the default.
2. `soft_background_transition`: continue only palette, lighting, texture, shadow, or gradient. Do not continue identifiable objects.
3. `graphic_connector`: continue one simple abstract line, steam curve, ribbon, or geometric panel. Specify its position, width, color, and direction on both slices.
4. `verified_object_continuation`: allow an identifiable object to cross the seam only with an actual previous-edge crop or outpainting context. Extend the source edge rather than redrawing it.

For every slice after slice 01, define:

- `transition_type`: one of the four types above.
- `edge_zone_percent`: a value from 8 to 12.
- `allowed_edge_elements`: the only visual materials permitted in the edge zone.
- `forbidden_edge_elements`: objects and critical content that must stay out of the edge zone.
- `previous_edge_reference`: the actual previous bottom-edge crop when using `verified_object_continuation`; otherwise `none`.
- `seam_audit_rule`: specific failure checks for that boundary, including duplicated objects, accidental cuts, color jumps, and connector drift.

6. Audit the result

   After generation, check whether the result reads as one continuous ecommerce detail page. Also check whether every visible selling point matches the image evidence mapped in `claim_visual_evidence`, the product drifted, text became garbled, layout hierarchy failed, unsupported parameters/certifications/claims appeared, or any final slice does not match the exact canvas selected in the approved blueprint. Give specific revision advice before proposing another generation pass.

   Continuity audit must inspect every adjacent pair immediately after the later slice is generated, starting with 01-02 and continuing through the boundary before the selected final screen. Also inspect the early 2-slice preview and the final full-page preview. Fail a seam when an object is duplicated on both sides; a table, wall, horizon, panel, person, hand, product, cup, card, or text block is accidentally cut; light direction changes at the boundary; background color jumps without an intentional divider; critical content touches the seam; a graphic connector changes position, width, color, or direction; or the later slice redraws the earlier slice's edge instead of extending it. Fail the whole result if slices repeat full poster structures, centered hero scenes, primary motifs at the same scale, or identical title/tag blocks. Passing slices must use either verified continuity or an intentional natural section break.

   For a generated 1:3 master, inspect the image before presenting the first batch. Check whether it visibly covers the complete selected screen range, contains the expected text modules or reserved text zones, reads as one long detail page instead of stacked independent scenes, controls repeated primary motifs rather than mechanically duplicating them, and lets every planned screen map to a distinct region or transition. If these checks fail, regenerate the 1:3 master before presenting screens 01-02.

   Route revisions to the smallest responsible layer instead of regenerating the full set by default:

   - Copy or wording failure: revise `text_exact` and regenerate only the affected slice or repair its text area.
   - Claim-evidence mismatch: revise `claim_visual_evidence`, `evidence_visibility`, `text_exact`, or the smallest responsible visual module; regenerate only the affected slice.
   - Product identity, orientation, color, shape, logo, or component failure: strengthen the product-reference constraint and regenerate only the affected slice.
   - Single-screen hierarchy or clutter failure: revise that screen's `primary_module`, `secondary_modules`, `content_density`, `copy_structure_pattern`, or `hierarchy_strategy`.
   - Adjacent-screen transition failure: revise the two affected edge anchors and regenerate the smallest neighboring slice range.
   - Repeated visual grammar across several screens: revise `composition_shift` for those screens; keep the approved narrative and unaffected screens.
   - Whole-page style or spatial continuity failure: revise the text master or 1:3 master, then regenerate only the slices influenced by the change when possible.
   - Whole-page narrative or claim-seed failure: return to the page blueprint. Use full regeneration only when the approved story itself changes substantially.

7. Deliver the image set

   After generation, revision, and final audit are complete, save the approved image set without adding a separate destination-confirmation step. If the user has already provided a destination, use it. Otherwise, create a clearly named delivery folder under the current workspace, such as `outputs/product-detail-page/<product-name>-<timestamp>/`. If there is no usable workspace, create the delivery folder beside the working source assets or in the active working directory. Preserve the original generated files.

   Deliver the complete set, not only preview images: the approved continuous 1:3 master for the selected screen range, every final individual slice with clear sequential filenames, the early 2-slice concat preview, the full-resolution final long-image concat, and an optional lightweight concat preview when useful. Do not include rejected or superseded variants unless the user explicitly asks for all iterations.

   Verify that every requested file exists in the delivery folder and that every final slice matches the selected exact canvas. At the end, report the delivery folder path and a short completion status so the user can open the folder and review the images. Do not ask the user to choose a save path after generation is already complete. Use clear names such as `product_master_01-<final>_1x3.png`, `product_screen_01.png` through `product_screen_<final>.png`, `product_first2_preview.png`, and `product_full_long.png`, replacing `<final>` with `10`, `12`, `14`, or `16`.

## Page Principles

- Make the first screen answer: what is this, who is it for, and why does it matter now?
- Prefer concrete capability language over vague adjectives.
- Let examples, parameters, screenshots, comparisons, and workflows carry credibility.
- Avoid nested cards, decorative blobs, generic gradients, and hero sections that hide the actual product.
- Keep headings proportional to their containers; do not use hero-scale type inside compact panels.
- Use stable dimensions for fixed-format UI such as tabs, toolbars, media frames, grids, counters, and feature tiles.
- Treat mobile as a first-class page, not a compressed desktop afterthought.

## Content Checklist

- Product name and category are visible immediately.
- Primary CTA matches the user's intended business or workflow goal.
- Capabilities are specific enough to be testable or recognizable.
- Sections are ordered by user decision flow, not by internal feature inventory.
- Technical claims include constraints, assumptions, or usage context when needed.
- The page includes enough concrete examples for a new visitor to understand the product.
- For image-led ecommerce pages, generated specifications, certifications, discounts, awards, and measured parameters are either provided by the user or clearly marked as placeholders to replace.

## Implementation Checklist

- Inspect existing components, routes, and styles before adding new abstractions.
- Use assets that show the product, output, workflow, or real subject matter.
- Confirm images, videos, canvases, or generated visuals render correctly.
- Check at least one desktop and one mobile viewport for overflow and overlap.
- Run available build, lint, or tests when the project provides them and the change scope warrants it.
- Report the local URL or file path the user can open.

## References

Read `references/detail-page-patterns.md` when choosing section patterns, adapting the skill to a specific product category, or reviewing whether a page structure is complete.
