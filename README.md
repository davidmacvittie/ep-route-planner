# EP Route Planner: a Claude skill for protective drive teams

A free [Claude](https://claude.ai) skill that builds a **route advance** for a small executive protection drive team (1 to 3 people) from just a list of addresses, a date and a time.

Created by **David MacVittie**. First public release: v1.0, November 2026.

## What it makes

A PDF route advance, 20 pages or so for a three-leg move, with:

- A how-to-read page, cover and trip timeline
- A map page per leg, then a primary and an alternate **strip map** (left turns above the line, right turns below, miles between turns, checkpoints) with a step-by-step table
- Predictable spots on each route, each with an "if blocked, go" plan
- Hospital runs turn by turn, and a rally point per stop
- A citywide events and closures check, and weather
- An overhead view of each stop with entrances, drop-off and pick-up points
- Green, amber or red verdicts, comms, and a hand-off to the site advance person

See [`sample/dc-route-advance-sample.pdf`](sample/dc-route-advance-sample.pdf) for a full example (Washington, DC, public places only).

## What you need

- A paid Claude plan with **Code execution and file creation** turned on (Settings > Capabilities)
- A mapping connector in Claude: **Mapbox** (first choice) or **TomTom**. Without one, the skill still works but marks routes and times as estimates to confirm.

Nothing runs on your computer. The skill uses only Claude's own tools.

## Install

1. Download [`ep-route-planner-skill.zip`](ep-route-planner-skill.zip).
2. In claude.ai, go to **Customize > Skills**, click **+**, then **Create skill > Upload a skill**, and pick the zip.
3. Start a chat and type something like:

```
Route advance please.
Start: The Willard InterContinental, Washington DC
Stops: The Anthem, 6:30 PM
       Fiola Mare, 9:15 PM
End: The Willard
Date: next Friday
```

Claude asks once for anything it can't assume, then builds the PDF.

## Feedback and suggestions

This is built for the EP community to improve. Please:

- **Comment or suggest ideas** in [Discussions](../../discussions)
- **Report a problem or a wrong output** with an [Issue](../../issues/new/choose)

Field experience is the most useful feedback: what you'd add, cut or reorder for a real 1 to 3 person team on a medium-threat US job.

## Important

This is a **planning aid, not a substitute for professional judgment or a physical recon**. Maps, traffic, closures, hospital details and event listings can be wrong or out of date. Always drive and verify the routes, and confirm every detail on the day. Never put a real client's name in a chat; the skill uses a code name by default.

## How to cite

See [`CITATION.cff`](CITATION.cff), or use the "Cite this repository" button on GitHub.

## License

Code and skill text: MIT (see [`LICENSE`](LICENSE)). Inter fonts: SIL Open Font License (see `ep-route-planner/assets/fonts/OFL.txt`).
