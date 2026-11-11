# PSYC 402 Encoding Strategies Demo

This is a **static HTML/CSS/JavaScript practice experiment** designed for deployment with GitHub Pages.

## What the experiment does

Participants complete three encoding blocks:

1. Maintenance rehearsal
2. Self-reference
3. Mental imagery

Each block contains six words. The order of the three encoding conditions is randomized across sessions. To reduce word-list confounding, the three six-word lists are also randomly assigned to the three encoding strategies.

After all three blocks, participants complete a 5-second backward-counting distractor task and then freely recall as many of the 18 words as possible.

The app automatically scores recall by encoding strategy.

## Files

- `index.html` — the webpage shell
- `styles.css` — visual styling
- `script.js` — experiment logic, randomization, scoring, and CSV export

## Important: data storage

This practice version **does not send data anywhere**.

At the end of a session, the user can download:

- a one-row summary CSV, and
- an 18-row trial-level CSV.

That is enough to demonstrate that a static website can generate analyzable data, but it is not a practical way to collect data from many participants.

For actual class data collection, the next step would be to connect the app to a service such as DataPipe so that each participant's data are sent automatically to instructor-controlled storage.

## Run locally

Double-click `index.html` to open the experiment in a browser.

## Publish with GitHub Pages

See the separate handout: `GitHub_Pages_Practice_Handout.docx`.


## DataPipe + redirect practice version

This folder now includes `config.js`. Paste your DataPipe experiment ID and the URL of the next GitHub project or Qualtrics survey into that file.

When the participant finishes free recall, the app automatically sends two uniquely named CSV files to DataPipe:

- `encoding_summary_<sessionID>.csv` — one row per participant/session
- `encoding_trials_<sessionID>.csv` — 18 rows, one per studied word

The app waits until DataPipe returns an accepted status for both files before automatically redirecting to the configured Qualtrics survey. If an upload is rejected or the network request fails, the participant remains on the page and can retry or download the CSV files locally.

If `PASS_SESSION_ID` is true, the redirect URL receives the anonymous session ID as a query parameter named `sid`. Example: `https://nextsite.example/?sid=ABCD1234`.
