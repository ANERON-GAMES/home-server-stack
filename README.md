# home-server-stack

A public index of the server software I run at home, and of the pieces that are safe to reuse.

The machine is a Windows home server. It serves a public site, a messenger, a smart-home plane, an AI plane, a gateway, and a mesh that talks to other computers in the house. Fourteen background services keep that stack up. The site is [anerongames.com](https://anerongames.com).

The production tree stays private. It holds keys, personal mail, device sessions, and the notes I use to operate the machine. These repositories are the reusable parts, rewritten so they contain none of that.

| Repository | What it is |
| --- | --- |
| [solar-clock](https://github.com/ANERON-GAMES/solar-clock) | Civil sunrise and twilight from latitude, and a local clock that refuses a sudden timezone jump. |
| [process-ledger](https://github.com/ANERON-GAMES/process-ledger) | One live process per role, with a start ledger and a rule for which duplicate to stop. |
| [api-grid](https://github.com/ANERON-GAMES/api-grid) | A health grid colored by response time. A fast error stays green. A dead probe keeps the last colors. |
| [job-lease](https://github.com/ANERON-GAMES/job-lease) | A job lease that accepts the result only from the same plane and the same worker. |
| [power-confirm](https://github.com/ANERON-GAMES/power-confirm) | Desired power is not truth until the device confirms it. A failed ON claim forces OFF. |
| [edge-presence](https://github.com/ANERON-GAMES/edge-presence) | Heartbeats from several paths, folded into online, degraded, or offline. |
| [path-grade](https://github.com/ANERON-GAMES/path-grade) | Grades a multi-path reachability sample so a slow origin is not blamed on the ISP, and a dead edge is not blamed on the origin. |
| [chat-pick](https://github.com/ANERON-GAMES/chat-pick) | Keeps the chat that was actually in use when several list the same participants, and merges overlapping message pages by id. |
| [peer-hold](https://github.com/ANERON-GAMES/peer-hold) | Realtime room peer state. A reconnect replaces the old peer, a silent peer is dropped, and stale signals are forgotten. |
| [chunk-reap](https://github.com/ANERON-GAMES/chunk-reap) | Plans orphan upload-chunk deletes with a grace window, a reference set, and separate rules for records and files. |
| [route-hold](https://github.com/ANERON-GAMES/route-hold) | A maintenance-mode path gate. Ordinary pages are held, while health, API, and static assets pass. |
| [circuit-trip](https://github.com/ANERON-GAMES/circuit-trip) | A circuit breaker state machine: closed, open, and half-open from failure counts and probe successes. |
| [batch-flush](https://github.com/ANERON-GAMES/batch-flush) | Decides when a batch should flush by count, bytes, age, or idle gap, without touching I/O. |
| [cooldown-map](https://github.com/ANERON-GAMES/cooldown-map) | A per-key cooldown and regenerating-charge tracker with a clock the caller supplies. |
| [backoff-plan](https://github.com/ANERON-GAMES/backoff-plan) | Capped exponential backoff with injected jitter and give-up rules. |
| [rate-window](https://github.com/ANERON-GAMES/rate-window) | Sliding-window rate limit decisions per key: allow or deny, remaining count, and retry-after, with a clock the caller supplies. |
| [quorum-vote](https://github.com/ANERON-GAMES/quorum-vote) | Folds up, down, and unknown health votes from several observers into one quorum verdict. One observer cannot change it. |
| [version-gate](https://github.com/ANERON-GAMES/version-gate) | Decides whether a client version may connect, connects with an update warning, or is refused. |
| [tick-budget](https://github.com/ANERON-GAMES/tick-budget) | A fixed-timestep accumulator that decides how many ticks to run per frame, with a catch-up cap. |
| [seq-window](https://github.com/ANERON-GAMES/seq-window) | A sliding 32-bit sequence window that accepts new numbers and flags duplicates or too-old ones, with wraparound. |
| [rank-shift](https://github.com/ANERON-GAMES/rank-shift) | Elo-style expected scores and rating updates with a configurable K factor. |
| [snap-lerp](https://github.com/ANERON-GAMES/snap-lerp) | A snapshot interpolation buffer that returns the bracketing pair and blend factor for a delayed render time. |
| [loot-roll](https://github.com/ANERON-GAMES/loot-roll) | Weighted loot rolls with a pity counter and an injected random source. |
| [idle-kick](https://github.com/ANERON-GAMES/idle-kick) | An idle-player policy that marks a player active, warned or kicked from last-input times. |
| [match-band](https://github.com/ANERON-GAMES/match-band) | A skill-band matchmaking queue whose band widens with wait time, up to a cap. |
| [aoi-grid](https://github.com/ANERON-GAMES/aoi-grid) | An area-of-interest spatial hash grid with radius queries and enter/leave sets. |
| [dead-reckon](https://github.com/ANERON-GAMES/dead-reckon) | Dead reckoning prediction with threshold-based snap or blend correction. |
| [rewind-buffer](https://github.com/ANERON-GAMES/rewind-buffer) | A lag-compensation history buffer that rewinds entity positions to a past server time for hit checks. |
| [spawn-pick](https://github.com/ANERON-GAMES/spawn-pick) | Spawn point selection scored by distance from threats and recent use. |
| [jitter-buffer](https://github.com/ANERON-GAMES/jitter-buffer) | A packet jitter buffer with sequence ordering and adaptive playout delay. |
| [clock-sync](https://github.com/ANERON-GAMES/clock-sync) | Client clock offset and round-trip estimation from timestamped ping samples. |
| [input-replay](https://github.com/ANERON-GAMES/input-replay) | A client input queue with server acknowledgement and replay for prediction reconciliation. |
| [ready-check](https://github.com/ANERON-GAMES/ready-check) | A lobby ready-check state machine with timeout, decline and quorum rules. |

Each library has tests and no network calls. The thresholds and the failure rules come from running this stack, not from a tutorial.

Vadim Gubin
[anerongames.com](https://anerongames.com)
