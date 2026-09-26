# F3 Coverage Assessment

A single-file browser tool for assessing fraud control coverage against the MITRE Fight Fraud Framework (F3), and for building an inventory of the controls behind that coverage and who owns them.

Built by Andrew Cunningham. Version 1.0.0.

**[Open the tool](https://ag-cunningham.github.io/f3-coverage-assessment/)** · [Download for offline use](../../releases/latest)

---

## What is it?

A self-contained HTML file that renders the full F3 matrix and lets a fraud team record which controls address which techniques, how well, with what evidence, and who is accountable for each control.

The entire framework is embedded in the file: 8 tactics, 123 techniques, 169 technique-and-tactic pairings, taken from MITRE's published F3 v1.1 data. There is no installation, no build step, and no internet connection required. Open the file in a browser and it works.

## Why was it created?

F3 gives fraud teams a shared vocabulary for describing adversary behavior. Turning that vocabulary into a clear picture of your own coverage is a separate exercise, and it is the one that produces something actionable.

## What does it do?

**Scores coverage per control, not per technique.** A technique can have any number of controls recorded against it, each with its own score and its own evidence note. The technique inherits the highest score of its controls, on the reasoning that a preventive control is not weakened by partial ones sitting beside it. Averaging would hide the strong control; summing would manufacture coverage that does not exist.

The scale:

| Score | Meaning |
|---|---|
| 0 · None | No control addresses this technique |
| 1 · Partial | Some coverage, with gaps in scope, channel, or timing |
| 2 · Detective | Reliably detected after the fact |
| 3 · Preventive | Blocked or materially disrupted before loss |

**Keeps one record per control, with an owner.** Each control is defined once, with its name and the team or function responsible for it, then linked to every technique it covers. Scores and evidence stay specific to each technique, because a control's effectiveness varies by context. The owner belongs to the control, so updating it in one place updates it everywhere.

**Builds a control inventory.** Every control is collected into one view showing its owner, each technique it covers, the tactic context, its score there, and the supporting note. The inventory can be sorted by name, owner, number of techniques covered, weakest score, or widest score range, and filtered by owner or by status: controls with no owner, controls that still need scoring, and controls not yet linked to any technique. This surfaces concentration risk and accountability gaps directly. A single control carrying coverage for fifteen techniques is a dependency worth naming before someone else names it, and a control with no owner is a finding in its own right.

**Generates a report.** Five optional sections (executive summary by tactic, full breakdown, gap assessment, control inventory, scope exclusions), formatted for letter paper with author, organization, and a "current as of" date. Control owners appear throughout, and the inventory section can be ordered by control name or by owner. Print to PDF, or save the page and open it in Word for editing.

**Exports in three formats.** A JSON assessment file that re-imports here and carries a framework version stamp, a flat CSV for spreadsheet work that includes control owners, and the printable report.

## How do you use it?

1. **Open the file.** Double-click it. Any modern browser works.
2. **Click a cell.** The panel opens with the technique description and a scoring guide.
3. **Record what covers it.** Choose "Add control" and search for the control. Pick it if it already exists, or create it if it is new and assign an owner. Score it and write the evidence for this technique. Repeat for each control that applies. If nothing covers the technique, check "No control in place." If it does not apply to your institution, check "Not applicable" and record why.
4. **Work across the matrix.** Cell color reflects the best score. Column headers track progress against in-scope techniques. Filters narrow by search text, framework origin, or coverage level.
5. **Review the control inventory.** Resolve any flagged duplicates, assign owners where they are missing, and score anything marked as needing it. Look for controls scoring inconsistently across contexts, and for controls carrying more coverage than expected.
6. **Build the report.** Choose sections, set the "current as of" date, add your name and organization, then print to PDF or save for Word.
7. **Export before you finish.** Work autosaves in the browser, but the JSON export is the durable copy and the one to share or version.

## Notes and limitations

- Assessments save to browser storage on the machine where the work is done. When the tool reopens with saved work, it says so and offers a fresh start. The JSON export is the file to keep.
- Some browsers block storage for files opened directly from disk, most often Safari. When that happens the tool shows a notice that autosave is off, and warns before the tab closes with unsaved work.
- If saved work in the browser came from a newer version of the tool, an older version leaves it untouched and pauses autosave rather than overwriting it.
- Loading a file replaces the open assessment, and the tool asks for confirmation first.
- Nothing is transmitted anywhere. All data stays in the browser on the local machine.
- Framework data is fixed at F3 v1.1. Exports record the version they were built against and warn on mismatch when a later version is loaded. Updating to a new F3 release requires regenerating the embedded data.
- Assessments exported from earlier versions of the tool import cleanly, and controls entered under slightly different spellings are combined on import.
- Scoring reflects the assessor's judgment. The tool structures and documents that judgment; it does not validate it.

## License and attribution

The tool is released under the [Apache License 2.0](LICENSE). See [NOTICE](NOTICE) for attribution.

Framework content © 2026 MITRE, from the [MITRE Fight Fraud Framework](https://github.com/center-for-threat-informed-defense/fight-fraud-framework), licensed under the Apache License, Version 2.0. The embedded technique data was converted from MITRE's published F3 v1.1 STIX bundle into the format this tool uses.

MITRE Fight Fraud Framework™, MITRE F3™, and MITRE ATT&CK® are trademarks of The MITRE Corporation. This project is not affiliated with or endorsed by MITRE.
