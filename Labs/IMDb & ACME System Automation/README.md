# Lab3 — IMDb & ACME System Automation

## Description

- This UiPath RPA project automates two separate web tasks:
  - Scrapes top movies from IMDb and saves details to text files.
  - Extracts work items from an ACME web system and saves rows to a dated text file.

## Features

- ACME workflow: opens a browser, logs in, navigates to the Work Items page, extracts rows, signs out, and saves results to `modules/ExtractedTextData/<date> _Items.txt`.
- Movies workflow: determines how many top movies to extract, opens a browser, navigates to IMDb top lists, extracts movie details (title, URL, rating, popularity, year/PG/duration, directors), and saves to `modules/ExtractedTextData/Top_<N>_Movies_on_IMDB.txt`.
- Reusable `SaveToNotepad.xaml` workflows write structured TXT output files. Example outputs are included in `modules/ExtractedTextData/`.

## Repository structure (important files)

- `Main.xaml` — project entry; orchestrates module invocations (currently contains commented-out invocations).
- `project.json` / `entry-points.json` — project metadata; `Main.xaml` is the entry point.
- `modules/ACME_SYSTEM/` — ACME module entry and helpers (`_MAIN_ACME_SYSTEM.xaml`, `OpenBrowser.xaml`, `Login.xaml`, `NavigateToWorkItemsPage.xaml`, `ExtractWorkItemsData.xaml`, `Signout.xaml`, `SaveToNotepad.xaml`).
- `modules/Movies Assistant/` — Movies module entry and helpers (`_Main_MoviesAssistant.xaml`, `GetNumberOfMovies.xaml`, `OpenBrowser.xaml`, `NavigateToTopMovies.xaml`, `ExtractMovieData.xaml`, `SaveToNotepad.xaml`).
- `modules/ExtractedTextData/` — output text files (examples: `Top_1_Movies_on_IMDB.txt`, `Top_2_Movies_on_IMDB.txt`, `Top_5_Movies_on_IMDB.txt`, `21_10_2025 _Items.txt`).

## How to run

1. Open this project in UiPath Studio (project created with Studio 25.x in VisualBasic expression language).
2. To run a single module:
   - Open its `_MAIN_*.xaml` (for example `modules/Movies Assistant/_Main_MoviesAssistant.xaml`) and click Run.
3. To run from the orchestrator `Main.xaml`:
   - Open `Main.xaml` and enable/uncomment the desired `InvokeWorkflowFile` activities, then click Run.
4. Outputs are written to `modules/ExtractedTextData/`.

## Configuration & important notes

- The workflows currently use absolute file paths (e.g. `D:\Study\...`). Convert these to relative paths or project-level configuration for portability.
- Inspect `Login.xaml` for credentials handling — do not store secrets in plain text. Prefer UiPath Orchestrator Assets or secure stores on production runs.
- Before running, validate and update UI selectors (they depend on browser and environment versions).
- Add retries and error handling for web interactions to improve reliability.

## Next steps (suggested)

- Make file paths configurable (project level or arguments).
- Replace any hardcoded credentials with secure assets.
- Re-enable orchestration in `Main.xaml` if you want the top-level process to run both modules.
- Ask me to inspect any specific workflow for a detailed walkthrough (for example `Login.xaml` or `ExtractMovieData.xaml`).
