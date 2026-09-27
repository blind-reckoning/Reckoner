# Blind Reckoning brand

The brand book for Blind Reckoning. Follow it for any UI, docs, README copy, packaging or user-facing strings.

## Files in this folder

- `tokens.css`: every color, spacing, radius and shadow token as a CSS custom property (`var(--chart)`, `var(--space-4)`), both themes, the `@font-face` rules and `.type-*` classes for the text styles. Link it and use the variables; never hard-code a hex value. Set `data-theme="night-watch"` on `<html>` to force dark, `data-theme="chart"` to force light; otherwise it follows the system setting.
- `tokens.json`: the same tokens as data, with a usage note on each.
- `fonts/`: Young Serif, IBM Plex Sans and IBM Plex Mono (SIL Open Font License).
- `logos/`: the mark, lockup and wordmark as outlined SVGs. Never redraw them.
- `symbols/`: the dead-reckoning and fix symbols.

Token names below (`chart`, `brass`, `sea`…) are the CSS variables without the `--`.

Blind Reckoning turns press-and-hold motorised blinds into Home Assistant covers. It cannot see where a blind is, so it works it out the way navigators did before GPS: from a known starting point, a known speed and the time elapsed. When the blind reaches fully open or fully closed, it takes a **fix** and clears any drift. The identity comes from the chart table: chart paper, navy ink, brass instruments and a red course line.

## Name

- Write **Blind Reckoning**: two words, both capitalised. Never "BlindReckoning", "Blind-Reckoning" or "BR" in prose.
- In code: `blind-reckoning` for the repository and packages, `blind_reckoning` for the Home Assistant integration domain.
- The hardware unit is a **Reckoner**: "fit one Reckoner per blind".
- Say "for Home Assistant". Never put "Home Assistant" in the name, the mark or a product title.
- Other people's work says "for Blind Reckoning" or "compatible with Blind Reckoning". Forks and clones that change the firmware or hardware use their own name and mark.

## Voice

Plain, precise, quietly nautical. Say what the device is doing in one sentence, then stop.

- Use navigation words only where they mean exactly the thing (see Vocabulary). Never as decoration: no "ahoy", pirates, anchors or rope.
- Sentence case everywhere except the `label` style. No exclamation marks, no emoji.
- Talk to "you"; the device is "it".
- Seconds take one decimal and a space before the unit: "23.4 s". Positions are whole percent, 0% closed and 100% open, matching Home Assistant.

Write like this:

> Took a fix at fully open. Corrected 0.8 s of drift.

> Heave the log: run the blind fully down, then press Stop the moment it lands.

> Position is estimated. It is confirmed the next time the blind reaches an end.

Not like this: "Arr, yer blinds be smart now!", "Revolutionary AI-powered shading."

## Vocabulary

| Term | Means | In the UI |
| --- | --- | --- |
| Fix | Position confirmed at an endstop | "Last fix: fully open, 2 h ago" |
| Drift | Timing error built up since the last fix | "Drift ±1.2 s" |
| DR position | Position estimated from elapsed time | "41% (estimated)" |
| Heave the log | The calibration run that times a full stroke | "Heave the log" button in setup |
| Heading | Direction of travel | "Heading up" |

The first time a term appears on a screen, put the plain meaning beside it.

## Logo

The mark is a semicircle and dot, the navigator's plotting symbol for a dead-reckoning position, rising over three slats. It also reads as a sun on the horizon, which is what blinds are for.

- `mark.svg` (brass arc, ink slats) on `chart` and `chart-raised`.
- `mark-reversed.svg` on the Night watch `chart` and on any `deep` fill.
- `mark-ink.svg` for one-colour print; `mark-white.svg` for PCB silkscreen and laser etching.
- `lockup.svg` / `lockup-reversed.svg` where the name must travel with the mark (README header, packaging, the device web page). `wordmark.svg` alone only where the mark already appears nearby.
- Clear space: a quarter of the mark's height on every side. Minimum size: mark 24 px (6 mm printed), lockup 120 px wide.
- Don't recolour it beyond these versions, rotate it, outline it, add compass needles, ships or anchors, or retype the wordmark in another face.

## Color

Two themes share every token name: **Chart** by day and **Night watch** by night.

- Ground is `chart`; panels are `chart-raised`; text is `ink`, secondary text `ink-muted`. `rule` is for decorative dividers only.
- `brass` is the identity: the mark, highlights and the drift state. Keep it to roughly a tenth of any screen. Brass words use `brass-text`, on `brass-soft` when tinted.
- `deep` with `on-deep` for the header band, hero panels and the primary button.
- States: a fix is `sea` with the Fix symbol; drift is `brass` with the word "drift"; a fault or Stop is `course`. Never carry a state by colour alone.
- Keyboard focus is the `focus-ring` shadow: a 2 px gap in the ground colour, then 2 px of solid `sea`.

## Type

- `display` (Young Serif) for page titles and the wordmark only. Never in device UI, never below 24 px.
- `heading`, `body` and `label` (IBM Plex Sans) for everything people read. `label` is set in capitals.
- `reading` (IBM Plex Mono) for the instrument readout: current position and travel time. `code` for entity IDs, YAML and firmware values.
- All three families are under the SIL Open Font License, so the firmware's web page can bundle them.

## Symbols

- `dr-position.svg`, a semicircle and dot on a baseline: position estimated by timing.
- `fix.svg`, a circle and dot: position confirmed at an endstop.
- Both are 24 px with a 2 px stroke, drawn in `ink`; always set a word beside them.
- For every other icon use Material Design Icons (`mdi:blinds`, `mdi:arrow-up`, `mdi:stop`), the set Home Assistant already uses, so the device page and the dashboard match.

## Imagery

Line drawings on chart paper: timing diagrams, the slat stack, a plotted course from open to closed. Photos show real installs in daylight and the hardware on a workbench. No stock oceans, ships or brass compasses as decoration; the metaphor lives in the words and the mark.
