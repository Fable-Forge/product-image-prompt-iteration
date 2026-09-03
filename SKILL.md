---
name: product-image-prompt-iteration
description: Use when creating, refining, or comparing product images, product renders, 三视图, three-view layouts, hero/detail renders, image prompt packs, or repeated visual prompt iterations where product identity, camera view, materials, text/logo handling, and version-to-version change control must stay consistent.
---

# Product Image Prompt Iteration

## Goal

Turn product visual requests into a controlled prompt-iteration workflow. Use this skill to keep product identity, view angle, material language, and change history stable across product images, three-view sheets, image edits, and prompt pack delivery.

This skill guides the prompt and review process. When the user asks to generate or edit images, use the available image generation or image editing tool after applying this workflow.

## When To Use

Use this for requests such as:

- 产品图, 商品图, 主图, 详情图, 概念产品图, 电商渲染图
- 三视图, front/side/back view, front/side/top view, orthographic product sheet
- prompt 连续迭代, 提示词优化, 提示词版本, prompt pack
- "上一版保留结构, 只改颜色/材质/镜头/背景"
- repairing generated product images while preserving the same object

Do not use this as a substitute for CAD, manufacturing documentation, product compliance review, or exact logo/text layout production. For precise labels, packaging copy, or brand marks, prefer a separate vector/layout step after the image is chosen.

## Required Inputs

Before iterating, identify these from the user request or ask only for missing details that materially change the result:

- Product identity: category, purpose, must-keep silhouette, functional parts, scale cues
- Output type: single hero image, detail render, three-view sheet, variants, or prompt-only package
- View contract: camera angle, orthographic versus perspective, number of views, background
- Visual language: materials, color palette, finish, lighting, brand mood, target buyer
- Constraints: forbidden changes, text/logo handling, realism level, aspect ratio
- End condition: selected final image, final prompt pack, comparison table, or next-iteration recommendation

If details are missing but the request is still actionable, make narrow assumptions and state them before generating or rewriting prompts.

## Workflow

1. Create a stable product brief.
   - Write one compact brief that names the product, silhouette, materials, colors, key parts, and intended use.
   - Separate stable identity from experimental variables. Stable identity should survive every iteration.
   - Do not invent real certifications, performance claims, dimensions, or brand ownership.

2. Define the iteration mode.
   - `hero`: one polished product image for presentation or ecommerce.
   - `detail`: close-up of a component, material, mechanism, or use state.
   - `three-view`: one product shown consistently across front, side, and back/top views.
   - `variant`: controlled alternatives where only one or two axes vary.
   - `repair`: fix a specific defect in an existing generated image.
   - `prompt-pack`: deliver reusable prompts without generating images.

3. Build the prompt spine.
   - Subject: exact product category and defining features.
   - Geometry: silhouette, proportions, visible parts, view angle, scale.
   - Materials: surface finish, texture, transparency, reflectivity, wear state.
   - Composition: framing, background, lighting, shadows, lens or orthographic setup.
   - Constraints: no text, no extra objects, same product across views, no cut-off edges, no distorted logos.
   - Output spec: aspect ratio, sheet layout, number of variants, and expected deliverable.

4. Iterate with change control.
   - Keep a short version log: `v1`, `v2`, issue found, exact prompt change, result.
   - Change the smallest prompt region that explains the defect.
   - Avoid changing product identity, camera, lighting, and style all at once unless the user explicitly asks for a reset.
   - For variants, vary one named axis at a time: material, colorway, camera, environment, or realism.
   - If an image is available locally, inspect it visually before deciding the next prompt.

5. Handle three-view requests strictly.
   - Specify a neutral orthographic product sheet unless the user requests perspective.
   - Put views in a clean grid with consistent scale and alignment.
   - Name the required views explicitly: front, side, back, top, or 3/4 as requested.
   - Require the same object, same proportions, same materials, same colorway, and no decorative scene props.
   - If text labels are not essential, omit them; image models often corrupt text.

6. Repair common image failures.
   - Identity drift: restate stable product brief and forbid changing silhouette or parts.
   - View mismatch: simplify camera language and require orthographic or single-axis rotation.
   - Extra props: add "product only" and remove lifestyle/environment language.
   - Bad text/logo: remove rendered text from the image prompt or move text to a later layout step.
   - Cropping: specify full product visible, centered, margins on all sides.
   - Inconsistent materials: restate material list and bind it to every view.

## Output Format

For active iteration, report:

- Current objective and assumptions
- Stable product brief
- Prompt used or proposed
- Version log with the specific change from the previous version
- Visual issues found and next recommended change
- Final selected prompt or prompt pack when done

For prompt-only delivery, include:

- `Base prompt`
- `Three-view prompt` when relevant
- `Variant prompts` only for requested variation axes
- `Negative constraints`
- `Verification checklist`

## Verification Checklist

Before calling the work complete, check the output against the request:

- Product identity stayed consistent across versions.
- Only intended variables changed between iterations.
- Three-view sheets show all requested views, aligned and at consistent scale.
- The object is fully visible and not occluded by props or text.
- Materials, colors, and key parts match the stable brief.
- Any text, logo, or label limitations are stated instead of hidden.
- Final output includes either the selected image/version or reusable prompt text.
