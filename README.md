# TsukubaUniv-waste-helper

Mobile-first beta web app for quick experimental waste-liquid sorting in an international laboratory environment.

Current release: `beta-v14.2`

This is an unofficial sorting aid based on the University of Tsukuba waste-management guideline used during development. It does not replace SDS, laboratory SOP, or the latest university instructions.

## What this tool does

This tool helps users search for a reagent name or mixed waste-liquid composition and returns one recommended waste category.

It is designed for:

- quick checks on mobile phones and desktop browsers
- Japanese, English, and Chinese users
- single reagents and mixed liquid waste
- common lab aliases such as `EtOH`, `MeOH`, `PFA`, `MilliQ`, `MQ`, `dH2O`, and `ddH2O`
- optional mixture composition input using percentage, volume, or mass

## Important safety scope

This tool assumes that the user has already confirmed the material is an experimental waste liquid or liquid mixture.

Do not use this tool to automatically classify:

- unused reagent bottles or obsolete reagents
- powders or solid waste
- animal, biological, infectious, or radioactive waste
- highly reactive, explosive, polymerizing, or unknown mixtures
- two-phase waste before phase separation

When in doubt, check SDS, laboratory SOP, and the responsible safety manager.

## Basic usage

Enter a reagent name or mixed waste-liquid components.

Recommended separator for mixtures:

```text
+
```

Examples:

```text
PFA
PFA + NaOH
ethanol + chloroform
EtOH + water
PFA + MilliQ
```

The tool displays only one highest-priority recommended category.

## Optional composition input

For mixed waste, optional composition fields appear automatically.

Supported formats include:

```text
80 mL EtOH + 20 mL water
60 mL EtOH + 40 mL water
95 mL EtOH + 5 mL chloroform
4 g PFA + 100 mL MilliQ
```

Mass units such as `g`, `mg`, and `kg` are treated as concentration information. They are not automatically treated as solid waste. If the concentration appears unusually high, the tool shows a warning and asks the user to confirm whether the material should really be handled as ordinary liquid waste.

## Current classification logic

The beta version follows these simplified priorities:

- halogenated organic solvent at or above 5 percent
- aqueous organic solvent when water or aqueous phase is at or above 40 percent
- general organic solvent waste
- waste oil
- inorganic waste liquid
- waste acid or waste alkali
- needs confirmation for special or unsupported cases

For two-phase waste, users should separate the phases and classify them individually.

## Language behavior

On first load, the interface follows the browser or device language:

- Japanese system or browser → Japanese
- English system or browser → English
- Chinese system or browser → Chinese

If the user manually selects a language, that choice is stored locally in the current browser.

## Feedback

The app includes an embedded Google Form for beta feedback.

The form automatically receives:

```text
app version
page language
search input
displayed result
```

Users can report:

- wrong classification
- missing reagent aliases
- mixture-ratio problems
- translation issues
- mobile UI problems
- other comments

A copy/download JSON fallback is available if the embedded form cannot load.

## Local data

Search history and language preference are stored only in the user's current browser using localStorage.

No search history is sent to a server by this app itself.

## Files

```text
index.html
CHANGELOG.md
README.md
.nojekyll
.github/workflows/pages.yml
```

The app is currently built as a single static HTML file for easy GitHub Pages deployment.

## GitHub Pages

Expected public URL:

```text
https://r0b0tao.github.io/TsukubaUniv-waste-helper/
```

If the page does not update immediately after a commit, wait for GitHub Pages deployment and refresh the browser cache.

## Changelog

See `CHANGELOG.md` for version notes.

## License and responsibility

This project is intended for internal beta testing and educational/laboratory support. Final disposal decisions remain the responsibility of the user and should follow SDS, laboratory SOP, and official university instructions.
