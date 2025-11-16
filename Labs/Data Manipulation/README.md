# Lab 2: UiPath - Data Manipulation

**Project:** UiPath automation exercises for Lab 2 — Data Manipulation (ITI course).

**Purpose:**

- Automate common data manipulation tasks (reading data from files, transforming/filtering data, and writing results).

**Repository Structure:**

- `Main.xaml`: Main UiPath workflow that orchestrates the automation.
- `project.json`: UiPath project metadata and dependencies.
- `entry-points.json`: Workflow entry points used by UiPath tooling.
- `project.uiproj`: UiPath Studio project file.

**Prerequisites:**

- Windows with UiPath Studio and UiPath Robot installed (use the UiPath Studio version compatible with the project files in this folder).
- If the workflow uses Excel activities, ensure the UiPath.Excel.Activities package is available (check `project.json`).

**Open and Run (UiPath Studio):**

1. Launch UiPath Studio.
2. Choose **Open > Project** and select this folder (where `project.json` is located).
3. In the Project panel, open `Main.xaml`.
4. Press the Run button (or use Debug → Run) to execute the workflow.

**Notes / Typical Tasks in This Lab:**

- Reading data from CSV or Excel into a `DataTable`.
- Filtering, sorting, or transforming `DataTable` rows.
- Writing processed data back to Excel/CSV or generating reports.

**Editing & Extending:**

- Open `Main.xaml` in UiPath Studio to inspect sequences, flowcharts, or invoked workflows.
- Check variables and arguments in the designer for inputs/outputs when modifying components.

**Troubleshooting:**

- If the project fails to open, confirm that `project.json` is present and that the UiPath Studio version supports the referenced activity packages.
- For missing packages, restore them via the Package Manager in UiPath Studio.
