# Project Guidelines

## Mandatory Development Checklist

Before finishing work, run `uv run ruff check .`, `uv run pytest`, and verify the app starts with `uv run uvicorn app.main:app --reload --host 0.0.0.0 --port 8000`. In this Windows workspace, if `uv` is not on `PATH`, use `py -m uv ...`.

## Architecture

Soc Ops is a small FastAPI app that renders Jinja2 templates and uses HTMX for fragment updates instead of a JSON API frontend. Keep route wiring in `app/main.py`, session state in `app/game_service.py`, pure bingo rules in `app/game_logic.py`, and shared typed models in `app/models.py`.

## Conventions

Keep handlers thin and move state transitions into `GameSession`. Preserve the server-rendered HTMX flow: endpoints should return HTML partials, usually from `app/templates/components/`, not JSON. Reuse the existing CSS utilities in `app/static/css/app.css` and keep new helpers typed and minimal.

## References

Link to existing docs instead of duplicating them: `README.md` covers the repo, `workshop/GUIDE.md` covers the lab flow, and `.github/instructions/css-utilities.instructions.md` covers styling utilities. Prefer extending existing assets under `.github/agents/` and `.github/prompts/` rather than introducing parallel conventions.
