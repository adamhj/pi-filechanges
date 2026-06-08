# filechanges (pi extension)

Tracks files changed (modified/created) by **pi** via the built-in `edit` and `write` tools.

## Origin and Credits

- This repository is a direct copy of `https://github.com/amosblomqvist/pi-config.git` (extension source).
- It is maintained as a standalone repo so it can be installed directly from GitHub in pi and customized independently.
- Special thanks to the original author: Eero Alvar (YouTube: `@EeroAlvar`).

## Installation

- Install from GitHub:
  - `pi install https://github.com/adamhj/pi-filechanges.git`
- Or install with git source syntax:
  - `pi install git:github.com/adamhj/pi-filechanges@main`
- Reload pi after install: `/reload`

## Features

- Persistent log (stored in session as custom entries)
- Status line + widget listing changed files
- `/filechanges` overlay to inspect diffs
- `/filechanges-accept` to clear the log (keep files)
- `/filechanges-decline` to revert logged changes (restore original contents / delete created files)

## Usage

1. Reload pi: `/reload`
2. Make changes through pi (using `edit`/`write`)
3. Run:
   - `/filechanges` to inspect
   - `/filechanges-accept` to accept (clear log)
   - `/filechanges-decline` to decline (revert)

### Non-interactive usage

If `ctx.hasUI` is false (print/json mode), accept/decline require explicit confirmation:

- `/filechanges-accept force`
- `/filechanges-decline force`

## Notes

- Only tracks changes performed through `edit` and `write` tools.
- To support “decline”, the extension stores the original file contents (before the first pi change) in the session file as a custom entry.
