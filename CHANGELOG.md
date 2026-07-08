# Changelog

## beta-v14.1

Released as the current beta for lab testing.

### UI

- Made the header non-sticky and reduced its height so it no longer covers page content.
- Moved language buttons to the upper-right area of the header on both desktop and mobile.
- Changed the shortcut label from “Go to search” to “Search”.
- Kept the mobile shortcut bar as a full-width sticky bottom bar.
- Changed the desktop shortcut area to a compact floating block at the lower-right corner.
- Added an `▲` button to return to the top of the page.
- Fixed the Japanese `フィードバック` button clipping in the desktop floating shortcut block.

### Classification and ratio logic

- Reframed the tool as a helper for waste liquids already confirmed as liquid experimental waste.
- Stopped treating mass units such as `g`, `mg`, and `kg` as automatic solid-waste indicators.
- Mass units are now treated as concentration information. High mass/volume values trigger a warning instead of direct classification.
- Aqueous solutions such as `PFA`, `formalin`, `NaOH`, `HCl`, `PBS`, and buffers are counted as aqueous liquid when entered with volume units.
- Organic solvent water content is estimated from the final liquid composition when volume or percentage ratios are provided.
- Halogenated solvent classification now uses the provided final-composition ratio when available, so low-percentage chloroform/DCM mixtures are not automatically forced into the halogenated category.
- Added a two-phase separation condition. When selected, the result asks the user to separate phases and classify them individually.

### Examples covered

- `60 g PFA + 40 mL MilliQ` now triggers a high-concentration warning and asks for confirmation instead of automatically treating it as ordinary liquid waste.
- `60 mL PFA + 40 mL NaOH` is treated as an aqueous liquid mixture containing an organic/formaldehyde component.
- `80 mL EtOH + 20 mL water` is treated as general organic solvent waste because water is below 40%.
- `60 mL EtOH + 40 mL water` is treated as aqueous organic solvent waste.
- `95 mL EtOH + 5 mL chloroform` triggers halogenated solvent waste by the 5% threshold.

### Feedback

- The embedded Google Form remains connected.
- Auto-filled fields remain unchanged:
  - `entry.569030736`: app version
  - `entry.2127042998`: page language
  - `entry.146557326`: search input
  - `entry.655882921`: displayed result

### Notes

This tool is still a sorting aid only. Final disposal decisions should follow SDS, laboratory SOP, and the latest University of Tsukuba instructions.
