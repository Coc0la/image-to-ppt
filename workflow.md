# Image to PPT Workflow

## Intake

Collect the available anchors:

- Source material: PDF, Word, spreadsheet, images, charts, screenshots, or dialogue notes.
- Presentation context: defense, report, research talk, product pitch, class presentation.
- Existing deck style: title band, background, color palette, card style, footer/navigation, and typography.
- Target output: whole slide, concept preview, separate images, annotated originals, or direct PPT editing.

If the user provides only a screenshot of a blank region, infer the approximate aspect ratio from the screenshot and create an asset that fits that region.

## Content Extraction

Read the source with this lens:

- Technical objects: algorithms, modules, hardware platforms, methods, datasets, channels, validation dimensions.
- Evidence: exact metrics, experiment settings, simulation curves, comparisons, and source figure captions.
- Message: what the slide must prove or make memorable.
- Boundaries: what is unfinished, difficult, proposed, or future work.

For academic defense slides, convert content into:

- Title: one direct topic phrase.
- Guide sentence: one horizontal sentence under the title.
- Main visual: chart, architecture, process, or comparison.
- Side/bottom cards: 2-4 short conclusions, each with one sentence.

## Style Extraction

From the existing PPT screenshot, note:

- Canvas ratio and approximate usable region.
- Header style: blue band, plain text, icon number, or school identity.
- Background: white, pale blue, technical lines, subtle illustration.
- Card system: border color, radius, shadow, fill colors.
- Accent colors: usually blue for structure, teal for data path, orange for algorithm or difficulty.
- Text density: defense pages should be sparse enough to explain orally.

Reuse the user's deck visual language rather than introducing a new theme.

## Generation Strategy

Choose the rendering method by risk:

- Use deterministic PIL/SVG/HTML for precise Chinese, tables, legends, numbers, and diagrams.
- Use image generation for illustrative conceptual visuals, photorealistic backgrounds, or creative thumbnails.
- Use local crop/upscale/sharpen when the user asks to keep an existing image's content unchanged.
- Use original figures as bases for annotated images; add arrows, short labels, and academic callouts.

Always save final images to the workspace, not only to a temporary generated-image folder.

## Modular Asset Patterns

Useful modules:

- Right-side conclusion card: narrow vertical `350x450` style for figure-heavy slides.
- Horizontal validation strip: `1300x162` style for four compact verification dimensions.
- Simulation setting card: one small card per channel/model/setting.
- Annotated chart: original curve plus arrowed labels placed near the relevant curve region.
- Implementation platform diagram: architecture chain plus bottom notes for platform scheme, parameters, or difficulties.

When the user asks for "same style" or "same ratio", copy the previous module's dimensions, colors, and typography.

## PPT Placement Heuristics

- For result slides, let figures take the majority of the page; put conclusions in a narrow side card.
- For method/process slides, use a central pipeline plus small cards around it.
- For settings slides, replace prose with small cards and a compact parameter table.
- For implementation slides, avoid claiming full hardware completion if the source only supports design/proposal; phrase as "platform design", "verification scheme", or "future closed-loop debugging".
- Put long caveats in speaker notes or small bottom row cards, not the main title.

## Revision Checklist

Before final delivery:

- Text is readable after insertion into PPT.
- No Chinese text is garbled, blurry, or outside a box.
- The image aspect ratio matches the intended blank region.
- The content does not overclaim beyond the source.
- File path is provided and the preview is shown when possible.
- If a PPT file was edited, render or screenshot the slide to verify placement.
