# Image to PPT

`image-to-ppt` is a Codex skill for turning documents, screenshots, charts, reference images, and conversation notes into PPT-ready visual assets and slide layouts.

It is designed for workflows where the user has source material such as a thesis PDF, Word document, simulation figure, existing PPT screenshot, or rough oral explanation, and wants Codex to produce concept visuals, annotated images, modular cards, or final slide-ready image blocks.

## What It Does

- Extracts slide-relevant information from PDFs, Word files, screenshots, charts, and dialogue.
- Consolidates long technical content into concise presentation messages.
- Matches the style of an existing PPT template or screenshot.
- Generates concept diagrams and academic visual explanations.
- Splits complex slide content into smaller PPT-ready image modules.
- Produces high-resolution PNG assets suitable for direct insertion into PowerPoint.
- Guides or performs image placement in PPT pages when requested.

## Typical Use Cases

- Create a research-method slide from a thesis.
- Annotate simulation result charts with academic advantages.
- Generate right-side conclusion cards for figure-heavy slides.
- Turn verbose simulation settings into compact visual cards.
- Create FPGA/SDR implementation diagrams from paper content and reference slides.
- Upscale or crop existing PPT figures for clearer reuse.

## Recommended Workflow

1. Provide source material: PDF, Word document, screenshots, charts, or text notes.
2. Provide a PPT screenshot or template if style matching is needed.
3. Ask for a concept layout first when the slide structure is uncertain.
4. Generate separate modules such as cards, strips, annotated figures, and diagrams.
5. Insert the generated PNGs into the PPT template.
6. Iterate on ratio, wording, clarity, and academic tone.

## Example Prompt

```text
Use $image-to-ppt to read my thesis PDF and current PPT screenshot, then generate a one-page research conclusion layout with separate right-side conclusion cards and annotated simulation figures.
```

## Files

- `SKILL.md`: Core skill instructions and trigger description.
- `references/workflow.md`: Detailed workflow and design heuristics.
- `agents/openai.yaml`: Codex UI metadata.

## Notes

For Chinese PPT content, the skill recommends deterministic drawing methods such as PIL/SVG/HTML when text precision matters. This avoids blurry or incorrect Chinese text often produced by pure image generation.
