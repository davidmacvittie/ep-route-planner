# EP Route Planner: a Claude skill for protective drive teams

A free [Claude](https://claude.ai) skill that builds a **route advance** for a small executive protection drive team (1 to 3 people) from just a list of addresses, a date and a time.

Created by **David MacVittie**. First public release: v1.0, November 2026. Current: v1.1 (simpler, more visual layout).

## What it makes

A PDF route advance, about 19 pages for a three-leg move with three routes per leg, kept visual:

- A how-to-read page, then a cover with general info, the timeline with verdicts, and weather
- A trip map with two labeled QR codes per place (a location pin and a Street View of the curb), and the events that touch the route
- A map page per leg: the route map and the drop-off's overhead view with its drop-off, backup and rally points
- A **strip map** per route (left turns above the line, right turns below, miles between turns, checkpoints) with a step-by-step table and notes, including an "if blocked, go" for every predictable spot, and a QR code that loads that route into Google Maps
- Three routes per leg by default (a primary and two alternates), or two if you ask
- Hospital runs turn by turn, and a one-page tick-box checklist for recon, day-of and comms
- Green or amber verdicts from public data; red is left to the team after the advance drive
- A blank recon log and an after-move note

See [`sample/dc-route-advance-sample.pdf`](sample/dc-route-advance-sample.pdf) for a full example (Washington, DC, public places only).

## What you need

- A paid Claude plan with **Code execution and file creation** turned on (Settings > Capabilities)
- Three connectors in Claude, all recommended. Connect them before your first run; the skill checks at the start and tells you which are missing.

| Connector | What it adds | Without it |
|---|---|---|
| **Mapbox** | The maps (trip map, leg maps, stop overheads), routes, turn-by-turn steps, drive times and address checks | Map pages show an empty box, and routes and times are marked as estimates to confirm on recon |
| **TomTom** | Live traffic, closures and roadworks, and alternate routes on short city legs | Closures come only from city DOT or 511 sites found by web search, and some short legs may have no alternate |
| **AccuWeather** | The forecast for the day of the move | Weather comes from web search, or the normal for the date if the forecast isn't out |

The skill still builds a packet with any of them missing, but it is less complete and says so.

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

You can also give a code name, the number of cars, who greets the car at the venue, and 2 or 3 routes per leg (3 if you don't say). Claude asks once for anything it can't assume, then builds the PDF.

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
