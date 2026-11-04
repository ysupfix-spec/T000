# WHOOP-inspired UI refresh

Analysis migration required: no

The default Liquid Today dashboard now shows Sleep, Recovery, and Strain as static circular gauges. The arcs retain the existing local scores, missing-data behavior, units, provenance, and navigation. This is a visual refresh, not WHOOP scoring or an official WHOOP app.

Shared Apple styling uses charcoal surfaces, white sans-serif/tabular numbers, compact rounded cards, blue strain and slate sleep accents. Dark card washes and drop shadows are removed. Light mode, increased contrast, transparency preferences, custom chart styles, and saved backgrounds remain supported. New installations use a plain canvas; existing explicit background preferences are respected. Other dashboard layouts retain their structure and inherit shared styling.

## Validation

- Source doc-comment lint passed.
- 42 WCAG palette/structural contrast checks passed (actual source tokens, light and dark).
- Updated the native chrome saturation test to allow the new subtle charcoal cast; retained the readability thresholds.
- Xcode, Swift and an Apple simulator are unavailable in this environment. Native compilation, native tests and visual/device QA have NOT been run.

## Build and review on a Mac

Follow docs/BUILD.md and docs/IOS.md. Run `xcodegen generate`, then build the NOOPiOS and Strand schemes. Review Today in both appearances, missing and full data, narrow widths, Larger Text, VoiceOver, and Increase Contrast. The refresh uses existing files, so no project source registration is needed.

The accompanying patch records every modified source file relative to the supplied 12.2.1-dx archive.

## Modified files

- Packages/StrandDesign/Sources/StrandDesign/Appearance.swift
- Packages/StrandDesign/Sources/StrandDesign/Components.swift
- Packages/StrandDesign/Sources/StrandDesign/NoopVisualStyle.swift
- Packages/StrandDesign/Sources/StrandDesign/Palette.swift
- Packages/StrandDesign/Sources/StrandDesign/StrandCard.swift
- Packages/StrandDesign/Sources/StrandDesign/TodayComponents.swift
- Packages/StrandDesign/Sources/StrandDesign/Typography.swift
- Packages/StrandDesign/Tests/StrandDesignTests/ChromeContrastTests.swift
- Strand/Liquid/LiquidTodayView.swift
