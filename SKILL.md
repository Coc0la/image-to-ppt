---
name: image-to-ppt
description: Transform documents, screenshots, charts, reference images, and user dialogue into PPT-ready visual content modules and slide layouts. Use when the user wants to build or refine a presentation page from PDFs, Word documents, existing PPT screenshots/templates, simulation figures, research results, diagrams, or image assets; when they ask for concept images, annotated academic figures, small card images, layout suggestions, or automatic placement of generated images into slides.
---

# Image To PPT

## Purpose

Use this skill to turn source material into presentation-ready visual assets. The ideal output is not only a picture, but a slide-usable system: concise content, a style matched to the user's existing deck, separate high-resolution modules, and a placement plan or edited PPT page.

For detailed execution heuristics, read `references/workflow.md` when the task involves more than a single image.

## Core Workflow

1. Gather source information.
   - Read PDFs, Word files, spreadsheets, screenshots, existing PPT pages, and the conversation history.
   - Extract only slide-relevant claims, numbers, labels, algorithm names, experiment settings, and conclusions.
   - Identify what is proven, what is proposed, and what is only a future/implementation difficulty.

2. Infer the deck style.
   - Use the user's PPT screenshots or template as the visual anchor.
   - Extract title style, background tone, accent colors, card radius, icon style, chart density, and common section structure.
   - If the user manually inserts generated images into a PPT template, optimize assets as transparent or white-background image modules with predictable aspect ratios.

3. Consolidate the content.
   - Convert long paragraphs into slide-sized claims.
   - Prefer one page with 2-4 message blocks over crowded prose.
   - Keep each annotation or advantage to one sentence unless the user requests detail.
   - Preserve exact technical terms and numeric results from the source.

4. Generate a concept image or layout preview.
   - Produce one overall concept page when the user is still deciding layout.
   - Use generative image tools for conceptual or illustrative visuals.
   - Use deterministic drawing (PIL/SVG/HTML) for Chinese text, numbers, tables, diagrams, and academic labels that must be crisp and correct.

5. Split into PPT-ready modules.
   - Generate separate small cards, right-side conclusion cards, horizontal validation strips, annotated chart overlays, or platform diagrams as independent PNGs.
   - Match the target blank region size or ratio when the user provides a screenshot.
   - Save all final assets into the current workspace or a clearly named output folder.

6. Place or guide placement in PPT.
   - If asked to edit a PPT/PPTX, use presentation tools and verify rendered pages.
   - If the user is manually inserting images, provide exact file paths, recommended placement, and any sizing notes.
   - Prefer fewer pages and larger figures for defense slides; use side cards only to summarize conclusions.

## Output Rules

- Make Chinese text crisp. Avoid model-generated Chinese text for precise labels; draw text locally when accuracy matters.
- Do not invent data. If a number or claim is inferred, mark it as inferred or omit it.
- Use high resolution by default: at least 2x the intended displayed size; 3x-4x for small text.
- Keep PPT modules visually calm: restrained blue/white academic style unless the source deck suggests otherwise.
- When improving screenshots, crop from the highest-resolution source and apply conservative upscaling/sharpening instead of regenerating content.
- For algorithm or research slides, distinguish traditional bottlenecks, proposed advantages, simulation settings, experiment results, and implementation difficulties.

## Common Deliverables

- `concept_page.png`: one-page layout proposal for user review.
- `*_card.png`: individual conclusion or method cards sized to PPT blank areas.
- `*_annotated.png`: original charts with arrows and academic annotations.
- `*_strip.png`: horizontal process or validation dimension strip.
- `*_hd.png`: cropped or redrawn high-resolution figure for direct insertion.
- Optional `.pptx`: final slide with generated assets placed and visually verified.

## Collaboration Pattern

Start by making a reasonable first version rather than asking many questions. Ask only when the slide size, target region, or required source is impossible to infer.

After showing a preview, expect iterative requests about ratio, wording, clarity, and academic tone. Keep the underlying generation script or editable source so the next revision is fast and consistent.
