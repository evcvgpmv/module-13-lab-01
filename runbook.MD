# Runbook for Module 13 Lab 01

This runbook is a concise instructor-facing guide to run through the Module 13 lab with students. It lists what to create first, why each step matters, and short tips you can use while teaching. Follow the steps in order during your class.

## Goal
Give students a hands-on introduction to the project's configuration and workflows (promptfooconfig.yaml). By the end of the lab students should be able to:
- Understand the repo structure and key configuration files.
- Run the project locally and verify expected behavior.
- Modify a simple configuration and observe the effect.

## Prerequisites (for instructor and students)
- Git installed
- Node.js (>=14) and npm installed OR Python/other runtime if the repo uses them (check README)
- Terminal/command-line access
- Basic Git knowledge (clone, checkout, status)

## Quick links
- Repository: https://github.com/niti007/module-13-lab-01
- Key config file used in this lab: promptfooconfig.yaml
  - View it in the repo: https://github.com/niti007/module-13-lab-01/blob/main/promptfooconfig.yaml

## Overview (what we are doing)
1. Inspect the repository and locate the `promptfooconfig.yaml` file — this defines configuration values students will change and test.
2. Create a local workspace (clone + optional branch) so each student can make changes safely.
3. Install dependencies and run the project locally.
4. Make a small, contained change in the config file and re-run to observe the change.
5. Discuss debugging steps and common pitfalls.

## Step-by-step (what to create first)
1. Clone the repository (first thing)
   - Command: `git clone https://github.com/niti007/module-13-lab-01.git`
   - Explanation: Provides the working files and the `promptfooconfig.yaml` used in the lab.

2. Create a new branch for the lab (recommended)
   - Command: `git checkout -b lab/module-13-<your-name>`
   - Explanation: Keeps student changes isolated and makes it easy to review later.

3. Inspect `promptfooconfig.yaml` (open and read)
   - What to look for: keys that change runtime behavior, placeholder values, and comments.
   - Teaching tip: Ask students to identify at least two fields they think will affect the app's behavior.

4. Set up local environment and install dependencies
   - If Node: `npm install` (or `yarn`), if Python: `python -m venv venv && pip install -r requirements.txt`.
   - Explanation: Ensures the app can run locally for testing config changes.

5. Start the application or run the relevant script
   - Typical commands: `npm start`, `npm run dev`, or `python app.py` — check repo README.
   - Verify: Open the app or run a test endpoint and confirm it works before making changes.

6. Make a controlled config change
   - Example: Modify a value in `promptfooconfig.yaml` such as a timeout, feature flag, or message string.
   - Save and re-run/reload the app.
   - Observe and record what changed.

7. Revert or commit changes
   - Either show how to `git restore --staged`/`git checkout --` to revert, or commit the lab branch: `git add . && git commit -m "lab: modify promptfooconfig for demo"`

## Verification and tests
- Provide one or two manual verification steps students should perform after changing config (e.g., reload page, run `curl` against an endpoint, check logs).
- If the repo contains tests, run `npm test` or `pytest` and confirm tests still pass.

## Common issues and troubleshooting
- Missing dependencies: re-run install and check error output.
- App won't start: check logs for missing environment variables referenced by `promptfooconfig.yaml`.
- YAML syntax errors: use an online YAML validator or `yamllint`.

## Teaching tips and timing
- 0–10 min: Intro + repo walkthrough
- 10–30 min: Environment setup and run the app
- 30–50 min: Guided config change + observe
- 50–60 min: Q&A, revert, and commit discussion

## Wrap-up
- Summarize what changed and why
- Encourage students to experiment with other config keys
- Optionally: open a PR from the lab branch and review the changes together

---

If you want, I can commit this runbook directly to the repository (as `runbook.MD`) so you and the students can access it from the repo root. I can also tailor the runbook to match the project's exact runtime (Node/Python) if you tell me which runtime the lab uses.