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

Auto-filled fields:

```text
entry.569030736  app version
entry.2127042998 page language
entry.146557326  search input
entry.655882921  displayed result
```

Changing the order of questions in Google Forms does not require changing these IDs. Regenerate the pre-filled link only if an auto-filled question is deleted and recreated, or if the form itself is replaced.

The “Expected category” question in the form can be made optional. That is usually enough for beta testing and avoids extra branching logic.

## GitHub Pages

Expected public URL:

```text
https://r0b0tao.github.io/TsukubaUniv-waste-helper/
```

If the URL returns 404 after the first commit, enable Pages in repository settings:

1. Repository Settings.
2. Pages.
3. Source: Deploy from a branch.
4. Branch: `main`, folder: `/ (root)`.
5. Save.

A GitHub Actions workflow is also included for Pages deployment where workflow-based Pages is enabled.

## Editing aliases

Most aliases are in the `R` array inside `index.html`. Add common lab names there first, especially abbreviations used by students and international researchers.

Important examples already included include `MQ`, `MilliQ`, `dH2O`, `ddH2O`, `DI water`, `ultrapure water`, `精製水`, `超纯水`, and related water names.
