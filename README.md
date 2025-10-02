### FFAStyles Prompt Library

A collection of JSON-based image prompt templates. Each file contains a structured object describing a visual style and output constraints. Paste your subject into the `object_specification.subject` field and adjust as needed.

### Metadata

Each style now includes a top-level `metadata` object for image-generation products:

```json
"metadata": {
  "type": {
    "category": "Elements / Stickers"
  }
}
```

- **type.category**: One of the following taxonomy buckets:
  - **Strokes**
  - **Shapes**
  - **Elements / Stickers**
  - **Images**

This field appears at the very top of every style file and can be used to filter or group styles programmatically.

- **Doodles**: Hand-drawn digital notes look. Clean black lines, minimal, no shading. White background.
  - File: `Default Styles/Doodles.md`
  - Best for: playful sketches, stickers, whiteboard notes
  - Example:
```json
{
  "object_specification": { "subject": "coffee mug" },
  "drawing_style": {
    "line_quality": { "type": "solid black ink" },
    "background": { "type": "solid white" }
  }
}
```

- **Wireframe**: Technical blueprint-style line work. Geometric, construction lines visible, no fill. White background.
  - File: `Default Styles/Wireframe.md`
  - Best for: product structure, CAD-like sketches, concept drafting
  - Example:
```json
{
  "object_specification": { "subject": "desk lamp" },
  "drawing_style": {
    "structure": { "perspective": "isometric" },
    "fill_and_texture": { "filled_areas": "none" },
    "background": { "type": "solid white" }
  }
}
```

- **Pictogram**: Ultra-minimal black silhouette built from basic shapes. Transparent background.
  - File: `Default Styles/Pictogram.md`
  - Best for: signage icons, sports symbols, universal pictograms
  - Example:
```json
{
  "object_specification": { "subject": "bicycle" },
  "drawing_style": {
    "color_palette": { "range": "solid black only" },
    "background": { "type": "transparent" }
  }
}
```

- **Vector Illustrator**: Flat vector illustration with bold outlines and transparent overlays for shading. Transparent background.
  - File: `Default Styles/Vector Illustrator.md`
  - Best for: app illustrations, marketing graphics, icons
  - Example:
```json
{
  "object_specification": { "subject": "backpack" },
  "drawing_style": {
    "lighting": { "type": "flat shading via overlapping shapes" },
    "background": { "type": "transparent" }
  }
}
```

- **3D Cute**: High-fidelity isometric 3D render with soft lighting and a white die-cut sticker border. Transparent background PNG.
  - File: `Default Styles/3D Cute.md`
  - Best for: product stickers, UI iconography with depth
  - Example:
```json
{
  "object_specification": { "subject": "game controller" },
  "drawing_style": {
    "perspective": "isometric",
    "background": { "style": "fully transparent alpha PNG" }
  }
}
```

- **Origami**: Handmade construction-paper origami assembly with visible paper textures and slight imperfections. Transparent background.
  - File: `Default Styles/Origami.md`
  - Best for: crafty, tactile visuals, playful subjects
  - Example:
```json
{
  "object_specification": { "subject": "fox" },
  "drawing_style": {
    "textures": { "material_finish": "matte construction paper surface" },
    "background": { "background": "transparent" }
  }
}
```

- **Textbook Diagram**: Clean, modern medical/textbook-style diagram with thin outlines and pastel fills. White background.
  - File: `Default Styles/Textbook Diagram.md`
  - Best for: educational diagrams, labeled figures (labels added separately)
  - Example:
```json
{
  "object_specification": { "subject": "human heart" },
  "drawing_style": {
    "line_quality": { "type": "thin, precise black outlines" },
    "fill_and_texture": { "filled_areas": "soft faded pastel fills" },
    "background": { "type": "solid white" }
  }
}
```

### Folders

- `Default Styles/`: curated templates included with this repo
- `Additional Styles/`: add your own styles here (kept with a `.keep` file)

### Quick usage

1. Open a style file (e.g., `Pictogram.md`).
2. Set `object_specification.subject` to your subject.
3. Keep background constraints as-is for consistent output.
4. Export using the indicated `output.format` and `canvas_ratio`.

Each `.md` contains the full JSON template with detailed fields for fidelity and consistency [[memory:6905418]].


