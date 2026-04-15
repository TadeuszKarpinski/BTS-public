<!-- Keep a Changelog guide -> https://keepachangelog.com -->

### [Unreleased]

### Added

- Added Module Groups for easier management of multiple modules.
- Braintec: Add option to open "Left" and "Right" diff files for translations export.
- Braintec: Add new commands "Tree Dependencies" and "Start DbGate".
- Braintec: Added actions via the 'ext' folder context menu: "Submodules: Sync with Project" and "Submodules: Update to Latest".

### Fixed

- Issue with starting actions for multi modules.
- Braintec: Open multi diff files for translations export.
- Braintec: Issue with diff files detection.
- Braintec: Move Check and Fix actions to Checks and Fix groups.

## [2026.4.2.242] - 2026-04-09

### Added

- Official music video for "Odoo Selector Pro" theme song.
- New drop database selection dialog.
- Support for testing the "Drop Database" command.
- Option to create recommended BTS Run Configurations - with or without --addons-paths.
- Alt attributes to images in README.md to improve accessibility.
- New macro \$BTSModulesWithI\$.
- Braintec: Auto update BT plugins.
- Braintec: Show notification with diffs for translations export.
- Braintec: Add new command Fix Ruff Unsafe.

### Changed

- Updated Gradle: 8.10.2 -> 9.4.1, Kotlin: 1.9.25 -> 2.3.20, Intellij Platform: 2.1.0 -> 2.13.1 and Jackson Dataformat XML: 2.17.0 -> 2.21.2. This optimization reduced the plugin size by ~45% (from 10 MB to 5.5 MB).
- Move texts and descriptions from plugin.xml to BtsBoundle.properties.
- Update README.

### Fixed

- Helpers in configuration.
- Organize imports.
- Code Quality.
- SVG icons.

## [2026.3.3.242] - 2026-03-25

### Changed

- Renamed plugin to "BTS: Odoo Selector Pro" because "Pro" is... more pro, like iPhone Pro.
- Removed outdated teaser from description.
- Updated README.

### Fixed

- Fixed issue with reading custom commands output

## [2026.3.2.242] - 2026-03-18

### Added

- Copy database and module names using Alt+Click or Alt+Enter.
- Concurrent background actions for refreshing lists, deleting/duplicating/renaming databases, with progress indication.
- Right-click on module combobox button will display modules context menu.
- Braintec: Tests and export translations can be run on the selected database.

### Changed

- Improved shortcut handling and descriptions in README and plugin.xml.
- Improved shortcuts and descriptions in documentation and UI (e.g., renamed "Addons Locations" to "Addons Paths").
- Database and module list refresh now runs in the background and does not block the UI.
- Braintec: Generating README for multiple modules now separates names with spaces instead of commas.
- Braintec: Translation export command changed from `generate-po` to `bt-translation`.

### Fixed

- Fixed issue with refreshing the database list after database operations.
- Improved searching across all modules.
- Braintec: Fix issue with reading bt command output.

## [2026.3.1.242] - 2026-03-03

### Added

- Braintec: Auto-refresh project view after generating PO files.

## [2026.02.3.242] - 2026-02-18

### Added

- Braintec: Add new command `generate-po` to generate PO files for translations.

## [2026.02.2.242] - 2026-02-17

### Added

- Braintec: Added actions for Odoo module testing: test group, test project modules, test non-project modules, test
  selected modules, test with coverage, and test with database removal.

### Changed

- Refactored Odoo module actions to use unified module selection (`getSelectedOdooModules`), improving reliability and
  maintainability.
- Improved shortcut handling and visibility logic for Odoo module actions.
- Braintec: Updated and streamlined scaffolding actions for Odoo modules (controller, migration, model, view, wizard).

## [2026.02.1.242] - 2026-02-03

### Changed

- Renamed plugin to "BTS: Odoo Selector AI" because slapping "AI" on it was cheaper than actually making it smarter

## [2025.12.1.242] - 2025-12-20

### Added

- Braintec: Added translation actions: "Generate PO" and "Select Languages" for Odoo modules.

### Fixed

- Fixed issue with fetching database list when Odoo is running, improving reliability of database operations.

### Changed

- Improved error handling and display of warnings when fetching database lists fails.

## [2025.12.0.242] - 2025-12-02

### Added

- Add new macro $BTSAddonsPaths$, which returns comma-separated list of selected addons paths.

### Changed

- Refactored command invocation logic in module actions for improved consistency and maintainability.
- Enhanced macros and configuration service for better state management and usability.
- Removed redundant code and streamlined command parameters across module actions.

## [2.1.76.242] - 2025-11-12

### Added

- Duplicate and rename database actions, with new icons for UI clarity.
- New macros for database and module selection, and test targeting.
- New macro for selecting tests.
- Braintec: Expanded scaffold options for Odoo modules: controller, group, migration, model, view, wizard.
- Braintec: Installation wrapper for bt commands, ensuring automatic installation if missing.

### Changed

- Split macros for more flexible usage.
- Improved command consistency and code quality across actions.

## [2.1.75.242] - 2025-10-13

### Added

- Color output for custom commands in the UI.
- Braintec: Scaffold, Check Licenses, and Check Dependencies actions for Odoo modules.

### Changed

- Improved dropdown actions: selected database is highlighted, context actions reordered.
- Filtered out odoo/addons locations and renamed paths to locations for clarity.
- Enhanced search in all modules and improved detection for custom projects.
- Refactored module actions and services for better speed, reliability, and code quality.

### Fixed

- Fixed issues with reopening the comboboxAction.
- Fixed code quality checks and search reliability.

## [2.1.74.242] - 2025-10-06

### Changed

- Configuration and documentation improvements.
- New documentation pictures.

## [2.1.72.242] - 2025-10-06

### Added

- Braintec: Context menu actions for Odoo modules: Check Quality, Generate Readme, Group, Select, Unselect.
- Braintec: Shortcuts for module selection: multiselect (shift), ctrl+click, ctrl+enter to jump/open module in tree
  view.
- Braintec: Actions: Check Quality, Generate Readme, PoFix, RuffFix, Unselect.
- Braintec: New shortcuts and context actions for Odoo modules.

### Changed

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

### Fixed

- Minor fixes for database handling and macro selection.
- Fixed issues with database selection and module actions.
- Resolved conflicts with other plugins and Odoo updates.

## [2.1.71] - 2025-09-23

### Added

- New Modules Selector UI for improved module selection and management.
- Macros for module selection and automation.
- New and updated icons for enhanced UI clarity.

### Changed

- Refactored and cleaned up code for module actions and services.
- Updated build files and documentation.
- Improved plugin.xml and configuration logic.
