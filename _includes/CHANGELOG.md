<!-- Keep a Changelog guide -> https://keepachangelog.com -->

# BTS Changelog

### [Unreleased]

#### Added

- Braintec: Auto update plugins.
- Braintec: Show notification with diff for translations export.

### [2026.3.3.242] - 2026-03-25

#### Changed

- Renamed plugin to "BTS: Odoo Selector Pro" because "Pro" is better than "AI".
- Removed outdated teaser from description.
- Updated description.

#### Fixed

- Fixed issue with reading custom commands output

### [2026.3.2.242] - 2026-03-18

#### Added

- Ability to copy database and module names using Alt+Click or Alt+Enter.
- Option to run Braintec tests and export translations on the selected database.
- Concurrent background actions for refreshing lists, deleting/duplicating/renaming databases, with progress indication.
- Improved shortcuts and descriptions in documentation and UI (e.g., renamed "Addons Locations" to "Addons Paths").
- Right-click on module combobox button will display modules context menu.

#### Changed

- Default Braintec translation export command changed from `generate-po` to `bt-translation`.
- Improved shortcut handling and descriptions in README and plugin.xml.
- Database and module list refresh now runs in the background and does not block the UI.
- Generating README for multiple modules now separates names with spaces instead of commas.

#### Fixed

- Fixed issue with refreshing the database list after database operations.
- Improved searching across all modules.
- Fix error with reading bt command output.
- Removed unnecessary code (e.g., the `wired` variable).

### [2026.3.1.242] - 2026-03-03

#### Added

- Auto-refresh Project View after generating PO files.

### [2026.02.3.242] - 2026-02-18

#### Added

- Add new Braintec command `generate-po` to generate PO files for translations.

### [2026.02.2.242] - 2026-02-17

#### Added

- Added actions for Odoo module testing: test group, test project modules, test non-project modules, test selected
  modules, test with coverage, and test with database removal.

#### Changed

- Refactored Odoo module actions to use unified module selection (`getSelectedOdooModules`), improving reliability and
  maintainability.
- Improved shortcut handling and visibility logic for Odoo module actions.
- Updated and streamlined scaffolding actions for Odoo modules (controller, migration, model, view, wizard).
- Enhanced configuration service and plugin.xml to support new actions and shortcuts.

### [2026.02.1.242] - 2026-02-03

#### Changed

- Renamed plugin to "BTS: Odoo Selector AI" because slapping "AI" on it was cheaper than actually making it smarter

### [2025.12.1.242] - 2025-12-20

#### Added

- Added translation actions: "Generate PO" and "Select Languages" for Odoo modules.
- Created a new "Translate" action group in the plugin menu.

#### Fixed

- Fixed issue with fetching database list when Odoo is running, improving reliability of database operations.

#### Changed

- Improved error handling and display of warnings when fetching database lists fails.
- Updated README with instructions for translation actions and new run configuration examples.

### [2025.12.0.242] - 2025-12-02

#### Added

- Add new macro $BTSAddonsPaths$, which returns comma-separated list of selected addons paths.

#### Changed

- Refactored command invocation logic in module actions for improved consistency and maintainability.
- Enhanced macros and configuration service for better state management and usability.
- Removed redundant code and streamlined command parameters across module actions.
- Update documentation.

### [2.1.76.242] - 2025-11-12

#### Added

- Duplicate and rename database actions, with new icons for UI clarity.
- Installation wrapper for bt commands, ensuring automatic installation if missing.
- Expanded scaffold options for Odoo modules: controller, group, migration, model, view, wizard.
- New macros for database and module selection, and test targeting.
- More scaffold actions for odoo modules.
- New macro for selecting tests.

#### Changed

- Split macros for more flexible usage.
- Updated plugin.xml and documentation.
- Improved command consistency and code quality across actions.

### [2.1.75.242] - 2025-10-13

#### Added

- Scaffold, Check Licenses, and Check Dependencies actions for Odoo modules.
- Color output for bt commands in the UI.

#### Changed

- Improved dropdown actions: selected database is highlighted, context actions reordered.
- Filtered out odoo/addons locations and renamed paths to locations for clarity.
- Enhanced search in all modules and improved detection for Braintec projects.
- Refactored module actions and services for better speed, reliability, and code quality.
- Updated plugin.xml and documentation.

#### Fixed

- Fixed issues with reopening the comboboxAction.
- Fixed code quality checks and search reliability.

### [2.1.74.242] - 2025-10-06

#### Changed

- Configuration and documentation improvements.
- New pictures.

### [2.1.72.242] - 2025-10-06

#### Added

- New shortcuts and context actions for Odoo modules.
- Actions: Check Quality, Generate Readme, PoFix, RuffFix, Unselect.
- Context menu actions for Odoo modules: Check Quality, Generate Readme, Group, Select, Unselect.
- Shortcuts for module selection: multiselect (shift), ctrl+click, ctrl+enter to jump/open module in tree view.

#### Changed

- BTS Command output now shown in Run tool window instead of Terminal.
- Improved plugin.xml and macro logic.
- No longer require odoo.conf for some actions.
- Refactored services and actions for reliability.
- Refactored and improved performance of module dropdown actions.
- Improved sorting and selection logic for modules.
- Enhanced plugin.xml and helper descriptions.
- Added ActionUpdateThread.BGT for context actions.
- Improved UI and usability for module selection.
- Improved error handling and user feedback for database operations.
- Enhanced logging for better debugging and support.
- Updated README and documentation for clarity and completeness.

#### Fixed

- Minor fixes for database handling and macro selection.
- Fixed issues with database selection and module actions.
- Resolved conflicts with other plugins and Odoo updates.

### [2.1.71] - 2025-09-23

#### Added

- New Modules Selector UI for improved module selection and management.
- Macros for module selection and automation.
- New and updated icons for enhanced UI clarity.

#### Changed

- Refactored and cleaned up code for module actions and services.
- Updated build files and documentation.
- Improved plugin.xml and configuration logic.
