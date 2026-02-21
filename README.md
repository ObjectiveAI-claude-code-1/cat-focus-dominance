# cat-focus-dominance

Scores whether a cat holds focus dominance in a photograph — whether it is the sharpest element relative to its surroundings. Evaluates subject clarity, background separation, and focal pull to determine if the optics direct the viewer's eye toward the cat as the intended subject.

## Input

The function accepts a single input:

| Field | Type | Required | Description |
|---|---|---|---|
| `photograph` | image | Yes | A photograph containing a cat situated within a scene. The image may come from any source — a professional portrait, a phone snapshot, or anything in between. |

The photograph should contain at least one cat along with surrounding visual elements. The function examines the interplay between the cat's sharpness and the sharpness of everything around it.

## Output

The function returns a scalar score between **0** and **1**.

- **Scores near 1.0** indicate strong focus dominance — the cat is distinctly sharp while its surroundings fall into softness, creating a natural and compelling focal pull toward the cat.
- **Scores near 0.5** indicate moderate or ambiguous focus dominance — the cat may be somewhat sharper than its surroundings, but the advantage is not decisive.
- **Scores near 0.0** indicate weak or absent focus dominance — the cat is blurry, no sharper than the background, or softer than its surroundings, causing the viewer's eye to drift away rather than toward it.

This is explicitly a measure of **relative** focus, not absolute sharpness. A slightly soft image where the cat is still the sharpest element will score higher than a uniformly crisp image where the cat enjoys no focal advantage.

## What It Evaluates

The function evaluates three qualities that together capture the full picture of focus dominance:

### 1. Subject Clarity

How crisply the cat itself is rendered. This examines whether the cat's features — fur texture, eyes, whiskers, body edges — are drawn with enough definition to register as the intentionally focused element. A cat with strong subject clarity feels present and tangible in the frame. A cat without it feels ghostly and approximate. This quality is not concerned with pixel-level perfection; it measures the perceptual sense that the camera found the cat and held it.

### 2. Background Separation

The degree to which the rest of the scene yields its claim on the viewer's attention. This compares the sharpness of the cat to the sharpness of its surroundings — whether the background dissolves into soft shapes and muted textures while the cat remains clear, or whether everything in the frame is rendered at a similar level of detail. Strong background separation elevates the cat from participant to protagonist. Absent separation leaves the cat as one element among many in a busy, undifferentiated scene.

### 3. Focal Pull

The emergent visual magnetism that draws the viewer's eye toward the cat and holds it there. This is the holistic, felt quality that arises when subject clarity and background separation work in concert — but is not fully explained by either alone. It captures whether looking at the cat feels inevitable, as though the image leaves the viewer nowhere else to go, or whether the cat is something the viewer must actively search for. Focal pull evaluates how sharpness gradients, contrast, and optical transitions converge on the cat to create a sense that the photograph is unmistakably *about* the cat.

## Use Cases

- **Photography curation**: Surface the best frames from a shoot by identifying images where the cat truly commands the scene, filtering out near-misses where autofocus locked onto a fence post or empty air behind the cat's ear.
- **Platform ranking and quality filtering**: Provide a visual salience signal for applications that display, rank, or recommend cat photographs — distinguishing between images where the cat is the star and those where it is merely present.
- **Pet photography evaluation**: Serve as a foundational building block for tools that assess or improve pet photography, measuring one of the most immediate qualities a viewer perceives about an image.
- **Automated feedback**: Power guided improvement workflows that help photographers understand whether their focus technique is directing attention toward their subject effectively.
