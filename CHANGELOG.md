# Changelog

## 1.1.0

Built against MITRE F3 v1.1. No storage schema change: autosaves and JSON exports from 1.0.0 open unchanged.

### Added
- **List view.** Every technique in one scrolling list, scored inline without opening each one. Edits save as you make them.
- **Bulk scope mode** in the matrix and list views. Select techniques, then exclude them, restore them, or add a rationale in one step. Bulk actions apply only to selected techniques visible under the current filters.
- **Save and Cancel in the technique panel.** Panel edits are a draft until saved. Closing with unsaved changes asks whether to save or discard. Ctrl+Enter saves.
- **"Out of scope, no rationale" filter**, plus a header flag showing how many exclusions lack a rationale. The report now marks these explicitly.

### Changed
- **Navigation.** Three sections: Framework, Control inventory, and Report. Framework offers a Matrix or List view, and remembers which one you used last.
- **Excluding a technique keeps its controls and any confirmed gap**, hidden rather than deleted. Restoring it to scope brings them back. The tool warns before excluding a technique that has work recorded.
- **Exclusions apply to every tactic a technique appears under by default**, with an option to limit it to one.
- A bulk rationale fills only exclusions without one, unless you choose to replace existing rationales.
- JSON export now includes controls recorded on excluded techniques.
