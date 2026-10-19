# Live Football Score

A live football scoreboard overlay for streamers (Kick, Twitch, YouTube) that follows Real Madrid matches and shows them on stream through OBS or Streamlabs.

- A floating glass capsule at the top of the screen with both clubs' logos, the score and the match clock.
- Goals open the capsule with an animation, the scorer's name, the minute and confetti in the scoring team's colours.
- Yellow and red cards, half-time, second half, added time and full time are announced automatically.
- The scorer list opens at every 10th minute (10', 20', 30' …).
- When there is no match today it shows the next fixture with the kick-off time in your local time zone.

Data comes from ESPN's public scoreboard JSON: free, no API key. Polls every 15 seconds while a match is live. ESPN usually runs a minute or two behind the broadcast.

## Use it in OBS

1. Download `overlay.html`.
2. In OBS add a **Browser** source, tick **Local file** and pick `overlay.html`.
3. Set width **1920** and height **1080**. The background is transparent.

Streamlabs: Add Source → Browser Source → Local File.

## Options

Add them to the address (untick *Local file* and use a `file:///…/overlay.html?…` URL):

| Option | What it does |
|---|---|
| `?demo=1` | Plays a scripted sample match |
| `?scale=1.2` | Bigger or smaller (e.g. `0.8`, `1.2`) |
| `?pos=bottom` | Moves the scoreboard to the bottom |
| `?team=86` | ESPN team id to follow (86 = Real Madrid) |
| `?debug=1` | Shows a status log of every request |

Combine with `&`, e.g. `?scale=1.2&pos=bottom`.

A Persian setup guide is in [guide-fa.md](guide-fa.md).
