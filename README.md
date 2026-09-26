# Mis Futbolistas Calendar

A small calendar-feed repository for **FC Barcelona** and the **Spain men's national team**.

The repository hosts `.ics` files that can be subscribed to from Apple Calendar and other calendar apps. The feeds are generated from the **Mis Futbolistas** Notion workspace, which is the source of truth for fixtures, kickoff times, venues, competitions, tracked players, and U.S. viewing information.

## Calendar feeds

### Barça

Raw subscription URL:

`https://raw.githubusercontent.com/ztamoz/mis-futbolistas-calendar/refs/heads/main/barca.ics`

### Selección

Raw subscription URL:

`https://raw.githubusercontent.com/ztamoz/mis-futbolistas-calendar/refs/heads/main/seleccion.ics`

## How the feeds work

The calendars include:

- confirmed fixture dates
- confirmed kickoff times when available
- venues when known
- competition and round information
- home / away status
- country flags for non-Spanish opponents where useful
- U.S. English- and Spanish-language viewing information when known

When a fixture date is known but the kickoff time has **not** been confirmed, the event is published as an **all-day event**. In Apple Calendar, these usually appear as a full-width colored bar. Once an official kickoff time is available, the event is updated to a timed event.

## Current workflow

The working pipeline is:

**Notion → `.ics` generation → GitHub → Apple Calendar**

1. Update the **Mis Futbolistas** Notion database first.
2. Regenerate the relevant `.ics` file.
3. Replace the matching file in this repository without changing its filename or path.
4. Commit the change to `main`.
5. Apple Calendar continues using the same subscription URL and picks up the revised feed on refresh.

Keeping the same event UIDs allows updated fixtures to replace existing calendar events instead of creating duplicates.

## Files

- `barca.ics` — FC Barcelona fixtures
- `seleccion.ics` — Spain national-team fixtures
- `README.md` — repository notes and update instructions

## Competition coverage

The Notion database tracks Barça and Spain across the competitions relevant to them.

**Barça:** LaLiga / Champions League / Copa del Rey / Supercopa de España

**Selección:** Nations League / World Cup / Euros / qualifiers

Fixtures are added when they are officially scheduled or become knowable after a draw.

## Notes

This repository is intended as a lightweight personal calendar-feed host. It is not an official FC Barcelona, RFEF, UEFA, LaLiga, Apple, or GitHub product.

Because the repository is public, anything stored directly in the `.ics` files should be treated as public information.
