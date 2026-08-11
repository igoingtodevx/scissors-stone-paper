# Schere · Stein · Papier · Godhand

A small browser prototype for a two-player game of rock-paper-scissors with an additional **Godhand** move.

## Status

This is a single-file prototype, not a production service. The complete implementation is `index.html`; there is no package manifest, build pipeline, automated test suite, server code, or persistence layer in this repository.

## Implemented scope

- Host-side PeerJS connection setup and guest joining by copied peer ID.
- Browser UI for Schere, Stein, Papier, and the one-use-labelled Godhand choice.
- Peer-to-peer exchange of choices, round outcome display, score counters, and round reset.
- Responsive styling embedded in the HTML file.

The page loads PeerJS `1.5.4` from a CDN at runtime. The source describes the connection as multiplayer P2P via WebRTC; a PeerJS signalling service is still required to establish the connection.

## Planned / not implemented

No roadmap is tracked in the repository. The following are not implemented: accounts, named rooms, server-side matchmaking, durable scores, reconnect handling, automated tests, and a hosted game service.

## Stack

- Static HTML, CSS, and browser JavaScript.
- PeerJS loaded from the external CDN at runtime.
- No npm, Python, or other application dependency manifest.

## Setup and use

Serve the directory from a local HTTP server so the browser has a stable origin:

```bash
python3 -m http.server 8000
```

Open `http://localhost:8000/` in a browser. One player starts as host and shares the generated peer ID from the input field. The second player pastes that ID and selects **Beitreten**. Both players then select a move, compare the result, and use **Runde leeren** for another round.

## Limitations

- A connection depends on the availability of PeerJS's external signalling/infrastructure and browser WebRTC support.
- Peer IDs, game state, and scores are held in memory only.
- The prototype has no authentication, moderation, persistence, or server-side validation.
- The repository has not been presented as having a verified production deployment.

## Public deployment

No verified anonymous public deployment was found for this repository.
