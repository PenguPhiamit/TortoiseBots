# Ported from TortoiseBots

Every file in `swg/` that comes from TortoiseBots by Sagiroth (<https://github.com/Sagiroth/TortoiseBots>), and where
it came from. Each ported file also keeps its own notice and gets a header with the same facts.

| File in `swg/` | Upstream path | Upstream commit | Licence | Upstream test ported |
|---|---|---|---|---|
| (none yet) | | | | |

## Planned

Sagiroth's original work, to be ported first (AGPL-3.0-or-later with the attribution term). Paths are at upstream
`64ffe51a` (v1.5.0).

| Upstream path | What the SWG port takes |
|---|---|
| `runtime/BotTurnScheduler.h` | The turn budget: a bot is due every 400 ms in combat, 1 s while dead, 3 s otherwise, most overdue first. Test: `tools/test_bot_turn_scheduler.cpp`. |
| `ai/playerbot/strategy/ActionFailureBackoff.h` | Bounded backoff for failed actions. Its header says its intent came from a donor reference; the notice stays as it is. Test: `tools/test_engine_failure_backoff.cpp`. |
| `runtime/ObservabilityEmitter.h`, `.cpp` | The event feed for a live map and dashboard. |
| `host/BotHostAdapter.h`, `.cpp`; `docs/HOST_API.md` | The host boundary and headless-session pattern, rewritten for Core3. |

Waiting for TortoiseBots' donor licence audit (`docs/LICENSE_AUDIT.md`): the engine (`Engine`, `AiObjectContext`,
`Strategy`, `Trigger`, `Action`, `Value`, `ReactionEngine`) and the strategies.

Not used: WoW content (classes, spells, raids, auction house, gear tiers).
