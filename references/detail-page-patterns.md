# Detail Page Patterns

Use these patterns as starting points. Adapt the structure to the product, audience, and existing project instead of copying every section.

## Ecommerce product detail page

Default behavior:

1. Resolve the page specification first. Default to `10` screens with exact `800 × 1200 px` (`2:3`) slices. If the user explicitly requests an extended supported format, use `12`, `14`, or `16` screens and/or exact `1080 × 1920 px` (`9:16`) slices. For any other screen count, pixel size, or ratio, ask the user to choose a supported format.
2. Output a structured page blueprint for the selected screen count and canvas, then wait for user confirmation.
3. After confirmation, create or confirm the long-scroll master specification: visual world, style DNA, typography lock, continuity motif, and section rhythm.
4. Generate or confirm a `1:3` continuous spatial master reference covering the complete selected screen range.
5. Generate final screens as sequential page-section images using the exact canvas approved in the blueprint.
6. Generate final screens in batches of exactly 2. After each batch, concatenate a small batch preview, inspect both screens and their seam, present the two screens and preview, then stop for explicit user confirmation.
7. Treat every revision request as approval withheld. Revise only the affected screen or batch, rebuild its preview, and wait again. Generate the next 2 screens only after the user confirms the current batch needs no further modification.
8. Use the `1:3` master as a spatial continuity anchor, not as a final output or crop source. Do not copy its layout, crop it, or replace the approved slice structure with it.
9. If splitting, keep the images as slices from one continuous page system. If the user wants one long output, concatenate the slices in order.
10. After full generation, concatenate the full set and audit product consistency, text quality, continuity, unsupported claims, and the selected exact canvas.
11. Save the approved image set to the user's specified directory, or automatically create a clearly named delivery folder under the current workspace when no directory was specified. Copy the master, every final single-screen image, the early concat preview, and the full-resolution final long image into it, then report the folder path.

Continuity rules:

- Treat the selected 10, 12, 14, or 16 screens as sequential segments of one ecommerce detail page, not independent posters.
- Use a shared art direction across the whole page: same background world, lighting, color palette, typography system, product rendering style, recurring visual motifs, and spacing rhythm.
- Prefer full-bleed slices and full-screen section boundaries. When adjacent scenes can connect, continue color, lighting, texture, shadow direction, simple lines, gradients, or verified edge content. When they cannot connect, end one full-bleed section and begin the next immediately instead of inserting a large blank band.
- Preserve product identity over frame coverage. Never distort, stretch, compress, over-enlarge, or redraw the product to force a full-screen composition. If full-bleed placement would change product proportions, shape, color, logo, handle, spout, controls, or distinctive components, reduce product scale and use restrained whitespace around the product while keeping the overall slice designed.
- Vary composition by zoom level and information hierarchy, not by changing the whole design language each screen.
- Keep recurring elements consistent when they exist: product shape, product material, ingredient style, character or model identity, icons, badges, CTA styling, and section dividers.
- If final delivery is 10 images, each image should feel like a page segment from the same long detail page. Do not generate 10 unrelated social-media posters unless the user explicitly requests poster sets.
- Prefer one master long-page prompt plus section-specific notes over 10 unrelated prompts.
- Use staged preview checks for every 2-slice batch. Present and confirm `01-02`, then `03-04`, then `05-06`, and so on; never generate the next batch while the current one has unresolved feedback. Concatenate the full set only after all batches are approved.
- Final prompts must create single vertical images using the selected exact canvas: default `800 × 1200 px` (`2:3`) or user-requested `1080 × 1920 px` (`9:16`). Do not generate `1:3` as the final page slice ratio.
- Text-only continuity instructions are weak. If each slice is generated as an independent image without visual context, the model often creates a complete standalone poster. Prefer ordered generation with edge references, outpainting/continuation context, or at least a concat-preview review loop after every few slices.
- A `1:3` spatial master can make continuity more stable. Use it to anchor the long page's background world, lighting direction, table/floor perspective, product scale rhythm, recurring motif rhythm, ingredient or prop flow, text hierarchy, and transition logic.
- Do not treat the `1:3` spatial master as a crop source. Final slices should use the selected exact canvas and be expanded page sections that inherit its spatial system while following their own structure blueprint.
- Avoid repeating the same full-screen pattern in every slice: big headline at top, primary subject beside product, product pile center, small badges underneath. A real long page changes density and composition while preserving the same visual world.
- After the hero slice, avoid repeating a full product-plus-primary-subject hero. Later slices may use partial crops, hands, background appearances, product details, props, environments, or no character/model at all, depending on the information task.
- After slice 01, headings should not make every slice feel like a new campaign opener. Use smaller hierarchy, integrated labels, macro evidence, environment continuation, or content modules to reduce standalone-poster closure.
- Each slice needs explicit top and bottom edge behavior. Reserve 8-12% at both edges as transition-safe content zones and keep main headlines, parameters, faces, hands, logos, complete products, and critical proof outside them, but do not turn those zones into automatic visible whitespace. Fill them with noncritical photography, wall/floor fields, texture, light, shadow, or other background content. Default to full-bleed `clean_section_break` or `soft_background_transition`; use restrained whitespace only when full-bleed treatment would deform the product or produce an inferior crop.

Use this when the user provides a product image or asks for a supported 10-, 12-, 14-, or 16-screen ecommerce detail page, product sales page, listing long image, or marketplace详情页.

Recommended screen order:

1. Hero screen: product name, category, primary visual, core selling point, and purchase-oriented CTA.
2. Pain point screen: the buyer problem, current workaround, or comparison against a common inferior choice.
3. Core benefit screen: the single strongest functional or emotional benefit, shown with the product in use.
4. Feature breakdown screen: materials, structure, dimensions, technology, ingredients, controls, or craft details.
5. Scenario screen: 3-5 realistic usage scenes matched to the target buyer.
6. Proof screen: certifications, reviews, before/after, durability, performance, warranty, or measurable evidence.
7. Comparison screen: model variants, competitor alternatives, old-vs-new, bundle contents, or value stack.
8. Final conversion screen: offer summary, guarantee, urgency when honest, shipping/returns, and final CTA.

Image-led workflow:

- Start by describing the visible product: shape, materials, color, texture, use clues, packaging, and implied category.
- Separate observed facts from inferred selling points.
- If confirmed selling points or specifications are missing, briefly invite the user to provide them before planning. If the user skips this, proceed and disclose that unconfirmed selling points are AI-inferred and require review.
- Analyze the reference image as style DNA, not just palette. If it has a clear 3D cartoon character, model pose, hand-held product reveal, camera angle, label style, or brand-host device, preserve that visual language in a product-appropriate way. Do not copy the reference brand, original person identity, text, or product.
- Do not invent regulated claims, medical claims, certifications, awards, or exact specifications unless provided.
- If the product category is unclear, create neutral copy that can be revised once the user confirms the category.

Output options:

- For planning tasks, provide a blueprint for the selected 10, 12, 14, or 16 screens with structure fields, copy modules, visual direction, canvas specification, and risk notes.
- For frontend tasks, implement the page as responsive sections and verify mobile scrolling, text fit, and image framing.
- For image-generation tasks, write a master long-page prompt first, then section-by-section prompts that preserve one continuous detail-page system.

Page blueprint fields:

- `slice_id`: sequential screen id, usually "01" through the requested count.
- `buyer_question`: the consumer question answered by this screen.
- `module_type`: internal section type such as `hero`, `benefit_scene`, `mechanism`, `function`, `detail`, `steps`, `scenario`, `parameter_trust`, or `faq_close`.
- `module_label`: short internal label for the section job. Do not use it as visible page text.
- `claim_seed`: one of the first-screen core selling seeds that this screen establishes or expands.
- `screen_job`: the independent information responsibility of this screen.
- `evidence_type`: the kind of proof or experience shown, such as product identity, lifestyle result, macro texture, ingredient/detail evidence, step sequence, pairing scene, trust note, or closing emotion.
- `claim_visual_evidence`: an explicit mapping from every visible selling point to the product part, action, scene, parameter graphic, comparison, or source note that supports it in the same slice.
- `evidence_visibility`: classify each mapped claim as `direct`, `contextual`, or `source_only`.
- `unsupported_visual_claims`: selling points the planned image cannot honestly support; remove them or change the visual plan before generation.
- `content_density`: `low`, `medium`, or `high`.
- `layout_archetype`: flexible layout intent, not a fixed template.
- `copy_module_type`: visible-copy form such as hero headline, guide title, explanatory paragraph, label cluster, ingredient notes, macro annotations, icon bullets, comparison snippets, scenario captions, trust bullets, or CTA microcopy.
- `copy_structure_pattern`: the sentence and text-module pattern for the screen, such as `hero_claim_stack`, `question_answer`, `single_line_with_labels`, `annotation_map`, `three_point_breakdown`, `scene_caption_cluster`, `mini_steps`, `trust_checklist`, or `quiet_closing`.
- `primary_module`: the main visual and message, including role, approximate area ratio, visual direction, and message.
- `secondary_modules`: 1-3 supporting modules when appropriate. Use them for proof, detail, tags, scenario cues, steps, trust notes, or light CTA support.
- `text_exact`: visible Chinese copy only. It may include `headline`, `subheadline`, `body`, `tags`, `labels`, `annotations`, `steps`, `trust_notes`, or `cta`, depending on the screen. Do not force all keys to appear.
- `hierarchy_strategy`: how text weight changes inside the screen, including which copy is dominant, which is supporting, and what stays small.
- `composition_shift`: how this screen changes visual organization from neighboring screens.
- `transition_type`: one of `clean_section_break`, `soft_background_transition`, `graphic_connector`, or `verified_object_continuation`.
- `edge_zone_percent`: the protected transition-safe percentage at the top and bottom, from 8 to 12. It protects critical content and does not require a blank strip.
- `top_edge_anchor`: what visual material carries in from the previous slice; keep critical text out of the top edge zone.
- `bottom_edge_anchor`: what visual material leads into the next slice; keep critical text out of the bottom edge zone.
- `allowed_edge_elements`: the only colors, textures, shadows, lines, gradients, or verified objects allowed inside the edge zone.
- `forbidden_edge_elements`: identifiable objects and critical content that must stay outside the edge zone.
- `previous_edge_reference`: actual previous bottom-edge crop for verified object continuation; otherwise `none`.
- `seam_audit_rule`: specific failure checks for the adjacent boundary.
- `visual_composition`: product, optional character/person/model, background, props, and module placement.
- `reference_style_notes`: what to borrow from the reference image's style without copying its product, brand, or identity.
- `risk_unknowns`: unsupported claims, ambiguous product facts, text-rendering risks, or product-drift risks.

Blueprint rules:

- Use the page blueprint as the highest priority source for final image prompts. Do not re-plan screens during prompt writing.
- One `slice_id` must map to one final image item. Do not merge two screen ids into one output.
- Every visible claim in `text_exact` must have a matching entry in `claim_visual_evidence`. Do not approve a blueprint when the selling point and planned image evidence are unrelated.
- Use `direct` evidence for visibly shown product parts, actions, materials, or supplied parameters. Use `contextual` for lifestyle and emotional illustration. Use `source_only` for confirmed facts that cannot be visually proven, and add a source or condition note.
- A lifestyle scene is not technical proof. Do not use people drinking, steam, water flow, icons, or attractive props to prove capacity, insulation duration, safety, leak resistance, material performance, durability, or cleaning performance.
- If the image cannot support a selling point, remove the selling point from `text_exact` or redesign the screen before generation.
- Adjacent screens must not answer the same `buyer_question`, repeat the same `screen_job`, or use the same `evidence_type` unless the second screen clearly changes proof angle.
- Screen 01 must establish 2-4 `claim_seed` values. Later screens must expand, prove, visualize, compare, or contextualize those seeds. Do not let screen 02+ introduce unrelated new selling points that screen 01 did not prepare.
- A good first screen seed set is broad enough to support the whole page but concrete enough to prove visually. Example for cookies: `巧克力豆满满`, `酥脆口感`, `金黄烘焙感`, `甜点分享时刻`.
- Later visible copy should sound like it is answering "why is that first-screen claim true?" or "how does that first-screen claim show up in use?" If it reads like a new campaign headline, rewrite it.
- `module_type` is an internal control. Convert it into natural buyer-facing copy; never display internal labels such as "detail", "parameter_trust", "FAQ", or "screen_job".
- `content_density` controls both copy and layout. High-density screens can have one strong primary module plus 2-3 supporting modules. Medium screens usually have a modest title plus labels, notes, or scene captions. Low-density screens may be atmosphere-led, but still need a clear product identity, transition, trust, or emotional role.
- `copy_structure_pattern` must vary across the page. Do not let screens 02-07 all use `headline + one explanatory sentence + three tags`. Vary question-answer, annotation labels, numbered micro-steps, scene captions, checklist notes, comparison snippets, sparse atmosphere copy, and closing CTA.
- `hierarchy_strategy` must prevent equal-weight collage. Every screen has one strongest memory point; secondary modules stay smaller, lighter, or more integrated.
- `composition_shift` must prevent adjacent screens from repeating the same visual grammar. Vary full-bleed scene, macro detail, diagonal flow, vertical sequence, integrated labels, quiet negative space, lightweight floating notes, and compact trust modules.
- `top_edge_anchor` and `bottom_edge_anchor` define visual carryover only. They should not contain main claims, critical text, or important product proof. Independently generated slices must not redraw identifiable neighboring objects inside these zones.

Copy hierarchy and section-weight rules:

- Treat the first screen as the main identity opener. It may use the clearest headline plus subtitle structure because it answers "what is this?" immediately.
- Do not make every later screen a new opener. Later screens should often use smaller guide copy, short explanatory lines, tags, labels, proof notes, ingredient/detail annotations, icon bullets, comparison snippets, scene captions, or CTA microcopy.
- Assign each screen an information weight before writing copy: high, medium, or low. High-weight screens can carry a visible title and multiple modules; medium-weight screens should combine a modest title with details or labels; low-weight screens may use only guide text, captions, badges, or atmosphere-led copy.
- Let copy form determine layout form. A proof screen may need callouts and annotations; a texture screen may need macro labels; a scene screen may need captions around a lifestyle composition; a trust screen may need compact bullets or checklist modules; a closing screen may return to a stronger CTA.
- Avoid repeating the same grammar rhythm across screens. A long page should feel like a narrative sequence with changing emphasis, not eight equal poster panels.
- If the planned copy for all screens can be represented as `headline + subtitle + product hero`, rewrite the plan before generating images.
- If three or more later screens can be represented as `headline + body + three tags`, rewrite at least two of them into different structures such as annotation-only, Q&A, mini-step sequence, scene-caption cluster, or checklist.

Copy differentiation rules:

- Adjacent slices must not repeat the same semantic promise with different wording.
- Each slice must answer a different buyer question. Examples: What is it? Why want it? What proves the taste? How does the texture feel? When do I eat it? Who can share it? What makes it feel trustworthy? Why buy now?
- Assign each slice a distinct copy role before writing headlines: identity, desire, proof, texture, scene, sharing, trust/detail, closing.
- Different roles should still unfold from the same first-screen seed set. "Different" means different proof angle, use case, visual evidence, or hierarchy, not unrelated selling points.
- Do not let every headline reuse the same words such as "香", "酥", "甜", "巧克力", "满满", or "一口". Repeated product keywords are allowed only when they serve a new information role.
- Body copy should introduce new evidence or context, not restate the headline.
- Tags should not all be taste adjectives. Mix product identity, usage scene, texture evidence, pairing, share occasion, and trust/detail cues.
- If three consecutive slices still feel interchangeable when read without images, rewrite the copy plan before generating images.

Post-generation audit:

- Batch concat preview: after every 2 newly generated slices, check whether they share one visual system without repeating identical poster structure. Present the preview with both individual slices for confirmation. Stop and revise until the user confirms the batch needs no further changes.
- Adjacent seam preview: after each later slice is generated, immediately concatenate it with its predecessor and inspect that one seam before continuing. Audit 01-02 through 09-10 individually.
- Full concat preview: after all slices, check the complete long-scroll rhythm, transitions, product consistency, text quality, unsupported claims, and repeated layout patterns.
- Product drift: color, shape, logo, material, window placement, handles, proportions, or included accessories changed.
- Text quality: headings are misspelled, unreadable, too small, or inconsistent across screens.
- Unsupported claims: invented parameters, fake certifications, medical claims, exact discounts, awards, or brand partnerships.
- Claim-evidence mismatch: headline, labels, annotations, or body copy describe a benefit that the same screen does not visibly demonstrate or qualify with a confirmed source note.
- Evidence visibility failure: the mapped evidence is missing, too small, visually unclear, contradicted by the generated product, or replaced by decorative imagery that cannot support the claim.
- Copy repetition: adjacent screens repeat the same taste promise, use similar headline grammar, or fail to answer different buyer questions.
- Continuity failure: the selected screen set looks like separate posters rather than one detail page, backgrounds reset too much, recurring identities or motifs drift, typography systems conflict, or section transitions are missing.
- Seam failure: duplicated objects appear on both sides; furniture, products, people, cups, cards, or text are accidentally cut; lighting or background jumps without an intentional divider; an abstract connector drifts; or a later slice redraws the earlier edge.
- Standalone-poster failure: each slice independently contains a complete hero composition, repeated product/primary-subject pairing, repeated tag badges, and no real edge carryover.
- Layout issues: weak hierarchy, cramped text, missing CTA, awkward crop, repeated compositions, or style mismatch.
- Revision advice: list concrete fixes and recommend whether to regenerate the full long image, one screen, or only the text/layout.

Delivery checklist:

- Use the user's destination when supplied; otherwise create a clearly named delivery folder under the current workspace without asking an extra question.
- Preserve original generated files and copy the approved outputs to the destination.
- Include the approved 1:3 master when used.
- Include every final individual slice with sequential filenames.
- Include the early 2-slice concat preview.
- Include the full-resolution final long-image concat; optionally include a lightweight preview copy.
- Exclude failed or superseded variants by default.
- Verify the destination files and report the final delivery folder path.

Revision routing:

- Copy problem: revise `text_exact`; regenerate or repair only that slice.
- Claim-evidence problem: revise the claim-to-visual mapping, evidence classification, copy, or smallest responsible visual module; regenerate only the affected slice.
- Product drift: strengthen product-reference constraints; regenerate only the affected slice.
- Single-screen layout problem: revise its modules, density, copy pattern, or hierarchy.
- Transition problem: revise neighboring edge anchors and the smallest affected slice range.
- Repeated layouts: revise `composition_shift` only for the repeated screens.
- Whole-page visual-system problem: revise the text/1:3 master and only the dependent slices when possible.
- Narrative problem: return to the blueprint; reserve full regeneration for substantial story changes.

## AI model or AI tool page

Recommended section order:

1. Product identity: model/tool name, category, primary capability, and one concrete user outcome.
2. Interactive or visual proof: output examples, generation previews, benchmark-style summaries, or workflow screenshots.
3. Capability map: what the product can create, transform, analyze, automate, or integrate with.
4. Use cases: 3-6 concrete workflows written from the user's perspective.
5. Controls and parameters: modes, quality settings, supported formats, limits, latency, safety, or pricing-relevant constraints.
6. Developer or operator details: API, integrations, deployment, permissions, or compatibility when relevant.
7. Comparison or upgrade path: why this page's product differs from prior versions or alternatives.
8. CTA: try, generate, sign in, view docs, contact sales, or download.

Avoid:

- Abstract hero copy without a visible product signal.
- Feature lists that do not show an output or workflow.
- Overstating model behavior without constraints.

## SaaS feature page

Recommended section order:

1. Feature name and operational promise.
2. Before/after workflow or task flow.
3. Key screens, tables, dashboards, or automations.
4. Team roles and permissions.
5. Integrations and data flow.
6. Metrics, reporting, auditability, or reliability details.
7. CTA tied to adoption: enable, configure, request demo, or read docs.

Design tone:

- Keep the page calm, dense, and scannable.
- Prefer clear tables, compact panels, and workflow diagrams over oversized editorial sections.

## Developer product page

Recommended section order:

1. Product/API name and what developers can build with it.
2. Quick code or request/response example.
3. Supported platforms, SDKs, models, formats, or endpoints.
4. Reliability, rate limits, auth, pricing-relevant constraints, and security.
5. Real integration examples.
6. Documentation CTA and sandbox CTA.

Design tone:

- Let code, diagrams, and concrete capabilities do the selling.
- Keep copy precise and avoid vague "build anything" language.

## Review rubric

Score each area as pass, needs work, or missing:

- First viewport clarity
- Specific capability communication
- Product-revealing visual assets
- Scannable structure
- Responsive layout
- CTA clarity
- Technical honesty
- Existing design-system fit
- Rendering verification
