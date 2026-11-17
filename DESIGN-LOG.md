# Design log

## 1. Button — feedback

| State | Primary | Outlined | Motion |
| --- | --- | --- | --- |
| Default | Pale green fill, dark text | Transparent fill, green outline and text | None |
| Hover | Lighter green fill | Lighter green fill, dark text | Color fades in 150ms |
| Focus-visible | 3px light-green ring, 4px offset | Same ring | None |
| Active | Darker green fill | Darker green fill, dark text | Moves down 2px |
| Disabled | Muted gray fill and text; not-allowed cursor | Not shown | No hover or press response |
| Reduced motion | Same hover and focus; darker active fill | Same | No press movement |

The buttons demonstrate states rather than submitting a form. The 150ms
ease-out transition keeps small feedback quick. The disabled example is a
native disabled button, so it is also unavailable to keyboard users.

## 2. Card and arrow — orientation

| State | Card and link | Arrow |
| --- | --- | --- |
| Default | Muted border; underlined link | Green, at rest |
| Hover on card | Green border | Slides right |
| Keyboard focus on link | Green border and visible focus ring | Slides right |
| Reduced motion | Border and focus feedback remain | Stays in place and turns white |

The card is the parent trigger; the link goes to the pulse section. The 250ms
ease-out is a little slower than the button because the arrow travels farther.
Hover is limited to devices that support it; keyboard focus has the same
orientation cue.

## 3. Pulse — attention

| State | Appearance | Motion |
| --- | --- | --- |
| Default | Green dot beside a descriptive label | Scales and fades in a 2s loop |
| Reduced motion | Solid dot with a static ring | Loop stops |

The slow ease-in-out loop is deliberately gentler than interaction feedback.
It is a decorative study, not a loading or live-status indicator.

## Choices

The design favors a small press and a short arrow slide over larger, more
distracting movement. A spinning loader was rejected because nothing on this
static page is loading. Reduced motion replaces movement with color and a
static ring, rather than removing the state cues.

## Previous challenge: button state matrix

| State | Background | Text | Outline | Motion |
| --- | --- | --- | --- | --- |
| Default | Accent | White | None | None |
| Hover | Accent, 15% darker | White | None | Background color fades with `--duration-fast` and `--ease-out` |
| Focus-visible | Same as default | Same | 3px focus ring, 3px offset | None |
| Active | Same as hover | Same | None | Scales to `0.97` with `--duration-fast` and `--ease-out` |
| Disabled | Light gray | Gray | None | No press movement; hover and active colors are overridden |

The secondary button uses a transparent background with accent text and border. Its hover state adds a subtle accent tint while keeping the outline.
