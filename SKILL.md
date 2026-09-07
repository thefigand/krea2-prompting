---
name: krea2-prompting
description: Use when turning an image idea, art brief, or Chinese visual description into a Krea 2 text-to-image prompt, especially when cinematic composition, subject scale, atmosphere, or stylistic coherence matters. Do not use for Stable Diffusion tag prompts or negative prompts.
---

# Krea 2 Prompting

Create one polished English prompt as flowing visual prose. Krea 2 responds better to a detailed, coherent scene than to comma-separated tags. Preserve the user's stated subject, action, colors, and spatial relationships; do not invent story-critical objects, IP, text, or conflicting style directions.

## Prompt construction

Use the relevant portions of this sequence. Omit a section rather than pad it with generic decoration.

1. Establish setting and mood: `A [adjective] [genre] scene set in [specific place].`
2. Add time, weather, light, and a few setting details that support the requested mood.
3. Describe the main subject in visual order: pose/action, appearance, face or expression when relevant, clothing, then props or interaction.
4. Establish depth with foreground, mid-ground, background, or distant elements where composition needs control.
5. State camera and composition explicitly: viewpoint/lens, framing, subject share of the frame, and what the remaining space emphasizes.
6. Close with a compatible art treatment: medium/style, palette, lighting, and texture. Add a restrained quality ending only when useful: `Masterpiece, ultra-detailed, highly textured, 8k.`

For detailed phrasing patterns and a complete example, read [references/krea2-prompt-patterns.md](references/krea2-prompt-patterns.md).

## Composition controls

| Intent | Prompt language |
|---|---|
| Emphasize place | `occupying only one-fifth (20%) of the frame, leaving the remaining space to highlight ...` |
| Balance character and world | `taking up nearly half of the foreground frame` |
| Ordered urban/interior scene | `occupies exactly one-third of the foreground frame, leaving the rest ... balanced with ...` |
| Add dynamism | `a slightly tilted Dutch angle` or `dramatic wide-angle fisheye lens effect` |
| Natural observation | `eye-level perspective` |

Use a single coherent camera plan. Do not combine close-up, tiny-subject, overhead, fisheye, and Dutch-angle directions unless the requested image genuinely needs all of them.

## Krea-specific constraints

- Write visible text in English quotation marks: `a neon sign that says "OPEN 24H"`.
- Do not generate a negative prompt. If the user asks for one, explain that Krea 2 uses CFG scale rather than negative prompting, then improve the positive description.
- When resolution is requested for Turbo, keep each dimension at or below 2K and divisible by 16.
- Favor intent and scene relationships over exhaustive pixel-level instructions.

## Output format

Unless the user requests alternatives, return only:

`Prompt (English):` followed by one ready-to-paste paragraph.

Optionally add one concise note only for a material caveat, such as a requested negative prompt or incompatible resolution. Do not translate the whole prompt back into Chinese unless asked.

## Final review

Check that the prompt has natural sentences, preserves the brief, gives the subject a clear action, has no accidental contradictions, and specifies lens plus framing when composition is important. Avoid tag piles such as `girl, forest, deer, 8k` and vague scale labels such as `large`.
