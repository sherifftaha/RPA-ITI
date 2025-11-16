# Lab1: UiPath Assistants — Movies & Weather

## Project Overview

This is a UiPath RPA project that contains two small assistants: a Movies Assistant (which searches and extracts movie information from the web) and a Temperature/Weather Assistant (which gets a city from the user and fetches weather information via Chrome). The project includes orchestration workflows and sample extracted text files.

## Repository Structure

- **`project.uiproj`, `project.json`, `entry-points.json`**: UiPath project files and entry-point definitions.
- **`Main.xaml`**: Top-level orchestration workflow (launches assistants).
- **`switch assistant.xaml`**: Router workflow to choose which assistant to run.
- **`Classic.xaml`**: Alternate or classic-style workflow (present in the repo).
- **`Modules/Movies Assistant/`**: Contains movie-related workflows:
  - ` _Main_MoviesAssistant.xaml`
  - `GetMovieName.xaml`, `SearchForTheMovie.xaml`, `OpenBrowser.xaml`, `ExtractMovieData.xaml`, `SaveToNotepad.xaml`
- **`Modules/Temp Assistant/`**: Contains weather/city workflows:
  - `_Main _Temp Assistant modern.xaml`
  - `GetCityNameFromUser.xaml`, `GetCityWeatherFromChrome.xaml`, `SaveToNotepad.xaml`
- **`Modules/ExtractedTextData/`**: Sample output and extracted text files such as `Top_5_Movies_on_IMDB.txt` and `endgame.txt`.

## How to Run

- **Prerequisites:**

  - UiPath Studio (open the `project.uiproj` file in UiPath Studio).
  - A supported browser (Chrome or Edge) with the UiPath browser extension enabled for web automation.
  - Ensure project dependencies in UiPath Studio are resolved (check the Packages pane).

- **Run steps:**
  1. Open the project by loading `project.uiproj` in UiPath Studio.
  2. In the Designer panel, open `Main.xaml` and run it (or open `switch assistant.xaml` to select an assistant interactively).
  3. To test a single assistant directly, open and run the assistant's main XAML: `Modules/Movies Assistant/_Main_MoviesAssistant.xaml` or `Modules/Temp Assistant/_Main _Temp Assistant modern.xaml`.

## Outputs

- Extracted results are saved as text files in `Modules/ExtractedTextData/` (for example, `Top_5_Movies_on_IMDB.txt`).
- Some assistants also save temporary outputs via `SaveToNotepad.xaml` components.

## Entry Points

- Entry points are defined in `entry-points.json`. Use the Entry Points pane in UiPath Studio to view and run them directly.
