# Instructor Quickstart (5–10 minutes)

Use this guide for your very first import. After this one-time setup, routine imports usually take 1–2 minutes.

## 1) Before you start (plain-language prerequisites)

You only need:
- A Google account you can use for Google Classroom.
- A copy of your course source file (the sheet or CSV your team provides).
- A copy of your materials file/folder (slides, links, or attachments your team provides).
- This project checked out on your computer.

## 2) First run (copy/paste commands)

Open a terminal in the project folder, then run:

```bash
cd /workspace/codex-test
python3 classroom_import.py --first-run
```

What you should see in the terminal:
- `Starting first-run setup...`
- `Opening browser for Google sign-in...`
- `Waiting for Google permission approval...`
- `Saved credentials. Setup complete.`

If your team uses a different input file name, run:

```bash
python3 classroom_import.py --first-run --input ./data/instructor_import.csv
```

## 3) Google login and consent screens (with screenshots)

When the browser opens, you will see a Google sign-in screen similar to this:

![Google sign-in example](browser:/tmp/codex_browser_invocations/9824afd7f51401cf/artifacts/artifacts/google-login.png)

What to do:
1. Enter your Google email.
2. Enter your password.
3. Complete 2-step verification if prompted.

Then Google asks you to approve access (OAuth consent). The exact text can vary, but it is typically an **Allow/Continue** screen tied to Classroom/Drive permissions.

![OAuth consent reference](browser:/tmp/codex_browser_invocations/9282f1373ec85a30/artifacts/artifacts/google-oauth-consent-doc.png)

What to do:
1. Confirm the account at the top is the one you want for Classroom.
2. Review permissions.
3. Click **Allow** (or **Continue**, then **Allow**).

After approval, return to the terminal and wait for `Setup complete.`

## 4) Routine imports (after first setup)

After first run, use:

```bash
cd /workspace/codex-test
python3 classroom_import.py --run
```

If needed, specify a file explicitly:

```bash
python3 classroom_import.py --run --input ./data/instructor_import.csv
```

Expected terminal messages:
- `Using saved credentials...`
- `Creating or updating Classroom...`
- `Posting materials...`
- `Import finished successfully.`

## 5) Troubleshooting

| Problem | What it usually means | Clear fix |
|---|---|---|
| Browser didn’t open | Your system blocked auto-open or no default browser is set. | Copy the login URL printed in terminal and paste it into any browser. Finish login there, then return to terminal. |
| Permission denied | The Google account cannot create/update Classroom data (or you clicked cancel). | Re-run first setup and click **Allow** on all required prompts. Confirm you are signed into the correct Google account. |
| Missing column | The import file header doesn’t match what the importer expects. | Open the CSV/sheet and add/fix the required header name exactly (same spelling/case), then run again. |

## 6) What success looks like

You are done when:
- Terminal shows `Import finished successfully.`
- A new (or updated) class appears in Google Classroom.
- Course materials appear in the class stream/classwork area.

Quick check:
1. Open [https://classroom.google.com](https://classroom.google.com).
2. Open the class created by the import.
3. Verify title, section, and at least one posted material.
