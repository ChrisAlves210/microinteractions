# Design Log

## Button State Matrix

| State | Background | Text | Outline | Motion |
| --- | --- | --- | --- | --- |
| Default | Accent | White | None | None |
| Hover | Accent, 15% darker | White | None | Background color fades with `--duration-fast` and `--ease-out` |
| Focus-visible | Same as default | Same | 3px focus ring, 3px offset | None |
| Active | Same as hover | Same | None | Scales to `0.97` with `--duration-fast` and `--ease-out` |
| Disabled | Light gray | Gray | None | No press movement; hover and active colors are overridden |

The secondary button uses a transparent background with accent text and border. Its hover state adds a subtle accent tint while keeping the outline.