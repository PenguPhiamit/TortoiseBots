# swg: TortoiseBots for a Star Wars Galaxies server

This branch builds on **TortoiseBots by Sagiroth**:

```text
Playerbots: TortoiseBots by Sagiroth — https://github.com/Sagiroth/TortoiseBots
```

It adapts TortoiseBots' design to a Star Wars Galaxies emulator server built on SWGEmu Core3
(<https://github.com/swgemu/Core3>). The server project is <https://github.com/PenguPhiamit/swg-138aby>.

Sagiroth gave permission for this fork, but is not involved in the port and has no ties to the server or to Star Wars
Galaxies. Report problems with anything in `swg/` here, on this fork, not upstream.

## Layout

- `main` mirrors upstream TortoiseBots and is never edited here. It is synced from upstream.
- `swg` (this branch) is upstream `main` plus one new top-level folder, `swg/`. Nothing outside `swg/` changes, so
  merging upstream into `swg` never conflicts. The WoW tree stays as it is; the SWG server does not build or use it.
- Inside `swg/`, as the port goes on:
  - `host/`: the Core3 host adapter, the one boundary between Core3 and the bot module (headless sessions, login and
    logout, the tick entry, the "counts as an observer" flag);
  - SWG strategies and their tests;
  - [`PORTED.md`](PORTED.md): every file ported from TortoiseBots, with its upstream path and commit.

Core3 itself gets only the narrow hooks the module needs, behind a CMake switch, so it builds and runs with the module
off.

## Status (19 October 2026)

Documentation only: no code is ported yet. The server's first bot milestone is being measured in its own Core3 tree, and
moves into `swg/` once it passes there.

## Licence notes

- **Original TortoiseBots work** is AGPL-3.0-or-later, with the additional attribution term in
  [`LICENCE.md`](../LICENCE.md) (AGPL-3.0 section 7(b)). Forks keep Sagiroth's credit and source link where TortoiseBots
  shows them. In the SWG port those places are a startup line in `core3.log`, a system message to every player at login,
  and a `/bot about` command. They go in with the first ported file and show the credit line above, plus a link to this
  source.
- **New files in `swg/`** are AGPL-3.0-or-later, the same terms as TortoiseBots' own work, so generic fixes can be
  offered upstream. Core3 is AGPL-3.0, the same family.
- **Ported files keep their notices.** Each one also gets a header naming TortoiseBots by Sagiroth, the upstream path
  and commit, and its licence. Donor files are never relabelled.
- **Engine and strategy code waits.** TortoiseBots' donor licence audit ([`docs/LICENSE_AUDIT.md`](../docs/LICENSE_AUDIT.md))
  is open. Until it clears a file, the port takes only Sagiroth's original work and writes its own engine from the
  design.
- **Network use.** Everyone who plays on a server running this code can get its source: the server project's repository
  and this branch.
- TortoiseBots' disclaimer in [`LICENCE.md`](../LICENCE.md) applies. Star Wars and Star Wars Galaxies are trademarks of
  Lucasfilm Ltd. and their respective owners; the server is a non-commercial fan project, not affiliated with or endorsed
  by them.
