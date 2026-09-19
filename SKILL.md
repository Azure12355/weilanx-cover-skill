---
name: xiaohongshu-cover
description: Generate or revise Chinese tutorial and experience-sharing covers in 3:4 by default or another requested aspect ratio, using a user-provided portrait or character reference, high-contrast Chinese typography, layered dark backgrounds, and topic-specific information collage elements. Use when the user asks for a Xiaohongshu, short-video, tutorial, knowledge-sharing, or high-impact social cover, especially when identity consistency and readable Chinese titles matter.
---

# Xiaohongshu Cover

Read [references/visual-style.md](references/visual-style.md) before generating a cover.

Use the portrait supplied by the user as the only identity reference. A second, optional image may be used as a visual-style reference. If either image is stored locally, treat it as private input and do not add it to this repository.

Fill in the prompt below with the user's requested aspect ratio, real topic, exact title, title line breaks, composition, and recognizable topic elements. Default to 3:4 when no ratio is requested. Then call the available image-generation tool directly. Do not write application code or invent engagement metrics. Return the generated image for the user to judge.

## Required input

- A portrait or person image supplied by the user.
- The exact cover title.
- The real topic or scenario.
- Optional: an explicit aspect ratio. Default to 3:4.

If the portrait is missing, ask the user to attach it. A style-reference image is optional.

## Generation prompt

```text
Create a cover for a Chinese tutorial, knowledge-sharing post, or experience recap in the requested aspect ratio. Default to a strict 3:4 vertical canvas when no ratio is supplied. Compose natively for the final canvas rather than generating one layout and cropping it. The composition should be rich in topic-relevant elements and stickers while remaining readable.

Input image roles:
- Image 1: the only identity reference. Use the person as a clean, photorealistic cutout from the original image.
- Image 2 (optional): visual-style reference only. Learn its general color balance, typography energy, information-card language, and density. Do not copy its layout, wording, person, logos, or element coordinates.

Topic: [real topic]
Aspect ratio: [3:4 default / 4:3 / 16:9 / 2.35:1 / exact user request]
Main title: “[exact title]”
Title line breaks: [write each line]
Person position: [left / right / centered]. The person is the second visual focus. Use only a solid white or warm-white outer stroke and a short dark shadow around the silhouette.
Composition: [asymmetric information collage / card matrix / path flow / central topic card / three-step tutorial / tool-and-file collage / side-by-side comparison / oversized-title poster]
Core topic graphic: [topic-specific graphic]
Topic elements and stickers: [8–12 real, recognizable elements in mixed sizes, such as a core graphic, information card, tool or file, state icon, arrow, path, node, cursor, magnifier, check mark, or warning sticker]
Information-card text: [only real, necessary, short labels]
Palette: [dark base + title colors + a small number of accents]

Overall style: dark but not cyberpunk, detailed but not chaotic, playful but not childish. The main title is the first visual focus. Set it in 2–4 lines of extra-bold Chinese display type with a thick black stroke, warm-white outer keyline, and short hard shadow. Use no more than three title colors, with one color per line. Information cards use dark fills, white outlines, short shadows, and restrained topic colors.

Layering:
- Foreground: place 2–4 prominent topic stickers or interaction elements. Never cover the person's face or the main title.
- Midground: place 4–7 varied cards, tool or file tiles, state cards, or process nodes around the person. Use short arrows, dotted lines, or paths to show meaningful relationships. Avoid a rigid software-dashboard grid.
- Background: add low-contrast topic silhouettes, file outlines, paths, node networks, code fragments, star maps, grids, dots, contour lines, dark clouds, or grain. Use only elements that support the topic.

Density and breathing room: fill corners and edges with subtle, coordinated detail without making the image thin or empty. Mix large, medium, and small elements across clear foreground, midground, and background layers. Keep clean breathing room around the face, hair, and main title. Preserve this hierarchy: title first, person second, core topic graphic third.

Background: use deep navy, indigo, aubergine, charcoal purple, or dark blue-purple rather than a large pure-black field. Background decoration must remain behind the person, title, cards, and small text.

Identity preservation: preserve the exact person from Image 1, including facial geometry, face shape, eyebrows, eyes, eyelids, nose, lips, hairline, individual hair texture, skin tone, natural skin detail, moles or freckles, facial hair, expression, gaze, lighting, shadows, clothing, pose, and body proportions. Do not redraw, regenerate, beautify, restyle, or over-smooth the person.

Keep the person as a clean photorealistic cutout from Image 1. Do not redraw, repaint, restyle, retexture, beautify, or regenerate the face, hair, skin, hands, or clothing. Preserve exact facial geometry, natural skin texture, pores, marks, facial hair, expression, gaze, lighting, and shadows. Background textures, grids, particles, paper grain, and decorative patterns are background-only and must never spill onto the face, hair, skin, hands, or clothing. No geometric lines, crosshatching, engraving, canvas texture, paper texture, plastic skin, smearing, asymmetrical facial features, or AI artifacts on the person.

Strictly preserve: identity, natural photographic texture, exact title text, visual hierarchy, and the requested aspect ratio.
Strictly avoid: copying the reference layout, extra people, face swapping, facial deformation, texture artifacts on the person, background texture leaking onto the person, cyberpunk, HUD interfaces, neon, glass, metal, rainbow lettering, saturated light washes, fabricated metrics, watermarks, and unrelated text.
All Chinese title characters must be accurate, clear, and complete.
```

## Editing an existing cover

Provide both the cover being edited and the original identity reference. Add this sentence to the beginning of the prompt:

```text
Only change [the requested area]. Do not regenerate the person region. Treat the original identity reference as the sole source of truth for the person.
```

## Multiple variants

Generate each variant or aspect ratio with a separate prompt and tool call. Recompose the title, subject, cards, and paths for every canvas instead of cropping one master image. Vary the composition or palette intentionally, and never overwrite an earlier result.
