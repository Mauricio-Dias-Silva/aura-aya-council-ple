# AURA-AYA Council (`aura-aya-council`)

Official Agent Harness entry for the **Google - Agent Harness on Physical-Engineering's Last Exam (PLE)** competition.

## Architecture Overview
- **Model:** `google-cloud/gemini-4-argon` (`AGY_EFFORT: "high"`)
- **Runtime:** [Antigravity / ADK-based harness](serve.py) using `taskbridge.py` and `task_mcp.py` over the PLE Harbor protocol.
- **Engineering Workflow:**
  1. **Rule 0 — Save-Early & Iterate:** Writes a complete, schema-valid initial version of all required deliverables early in the step budget (steps 12–15), then iteratively verifies and refines on disk.
  2. **AYA 4-Perspective Council Loop:** Enforces multi-disciplinary verification across structural/physical constraints, domain codes (NFPA/ASCE/NEC/ASHRAE), 3D/geometric clash and tolerance checks, and final deliverable schema validation.

## Repository Contents
- `submission.yaml` — PLE harness manifest (`google-cloud/gemini-4-argon`, `AGY_EFFORT: "high"`).
- `serve.py` — Agent harness entrypoint and system mandate.
- `taskbridge.py` / `task_mcp.py` — Task execution bridge and MCP tool server.
- `install.sh` / `requirements.txt` — Container dependency setup.
- `LICENSE` — Apache License 2.0.

## Reproducing Locally
Using the official [PLE starter kit](https://github.com/google-deepmind/physical-engineerings-last-exam) (or compatible runner):

```bash
# 1. Validate & smoke-test the harness
uv run python -m kit check /path/to/aura-aya-council-ple

# 2. Run evaluation on public dev tasks
uv run python eval/run.py /path/to/aura-aya-council-ple --artifacts
```

## License
Software and agent harness code is licensed under the **Apache License 2.0** (see `LICENSE`).

