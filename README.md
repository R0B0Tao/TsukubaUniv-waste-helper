# TsukubaUniv-waste-helper

Mobile-first beta web app for quick experimental waste-liquid sorting in an international laboratory environment.

Current release: `beta-v12`.

This tool is based on the University of Tsukuba waste-management guideline supplied during development. It is a sorting aid only. Final disposal should follow SDS, laboratory SOP, and the latest university instructions.

## Current beta features

- Japanese, English, and Chinese interface.
- Initial language is selected from the user's browser or device language.
- One search box for single reagents and mixed waste liquids.
- Recommended mixture separator: `+`, for example `ethanol + chloroform`.
- Optional composition fields for percentages, volume, mass, and simple solid-liquid preparations.
- Local search history stored only in the user's current browser.
- Embedded Google Form feedback with auto-filled app version, page language, search input, and displayed result.
- Copy/download JSON fallback if the embedded form cannot load.

## Feedback form

The current Google Form is wired in `index.html`:

```text
https://docs.google.com/forms/d/e/1FAIpQLScsgbzODHKkEoAtLp0RveVNZKgzeimLg5iLHHV0LB6f8bbO9A/viewform
```

## GitHub Pages

Expected public URL:

```text
https://r0b0tao.github.io/TsukubaUniv-waste-helper/
```
