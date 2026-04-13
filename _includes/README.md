<!-- Plugin description -->

Your **Odoo** control center inside **PyCharm**. Switch **databases** and manage **modules** without the usual hassle.

- **Switch databases instantly** - no config editing, no restarts, just one click.
- **Manage modules faster** - search, install, update, test - all in one place.
- **Generate run configs in one click** - no guesswork, no copy-paste, just working setups.

<blockquote style="background-color: rgba(76, 175, 80, 0.1); border-left: 5px solid #4CAF50; padding: 15px;">
  <b style="color: #4CAF50;">✅ Quick 3-Step Setup:</b>
  <ol style="margin-top: 10px; line-height: 1.6; font-weight: bold;">
    <li>Configure <span style="font-weight: normal;">your fetch database command.</span></li>
    <li>Auto-Generate <span style="font-weight: normal;">BTS Run Configurations.</span></li>
    <li>Adjust <span style="font-weight: normal;">the newly created Run Configurations.</span></li>
  </ol>
  Follow the guided instructions in the <b>How to Setup</b> section.
</blockquote>

## Official Music Video

[![Official Music Video](https://raw.githubusercontent.com/TadeuszKarpinski/BTS-public/refs/heads/main/images/BTS.jpg)](https://odoo.fail/bts/video)

## What's Inside
* [Database Selector](#database-selector)
* [Module Selector](#module-selector)
* [Test Selection](#test-selection)
* [Context Menu](#context-menu)
* [Run Configurations](#run-configurations)
* [How to Setup](#how-to-setup)
* [Custom Integration](#custom-integration)

## Links
* [Website & Documentation](https://bts-odoo-selector.com/)
* [JetBrains Marketplace](https://plugins.jetbrains.com/plugin/26426-bts-odoo-selector-pro)

## Database Selector

Use the `$BTSDatabase$` and `$BTSDatabaseWithD$` macros directly in your Run Configurations for seamless database switching. Alternatively, the tool can update the `db_name` in your `odoo.conf`.

![Animated demonstration of the Database Selector in Pycharm](https://raw.githubusercontent.com/TadeuszKarpinski/BTS-public/refs/heads/main/images/db_selector_2.gif)

* **Refresh** – Auto-updates on startup and config changes. Manual refresh needed after database operations.
* **Database** – Use the `$BTSDatabase$` or `$BTSDatabaseWithD$` macros in your Run Configuration for dynamic switching, or choose to automatically update the `db_name` in your `odoo.conf`.
  * `Delete` – Automatically configured for Braintec, PwC, and Ventortech.
  * `Duplicate` / `Rename` – Braintec exclusive.
* **All Databases** – Showing all databases.
* **Custom** – Enter a `db_name` and run your install config to spin up a fresh database.
* **Configure** – Advanced settings and automation:
  * `Fetch / Drop Databases` – Commands to fetch or delete databases (Auto-configured for partner environments).
  * `Path to odoo.conf` – Set a custom path for your configuration file (Auto-configured for Braintec, PwC, and VentorTech).
  * `Predefined Databases` – Set up your own list of go-to database names.

<blockquote style="background-color: rgba(120,169,255,0.15); border-left: 5px solid #61c4ff; padding: 15px;">
  <b style="color: #3879b3;">💡 Pro Tip:</b>
  <ul style="margin-top: 10px; line-height: 1.6;">
    <li><kbd>Left-Click</kbd>: Start typing to find your database.</li>
    <li><kbd>Middle-Click</kbd>: Fold.</li>
    <li><kbd>Alt</kbd> + <kbd>Click</kbd> or <kbd>Alt</kbd> + <kbd>Enter</kbd>: Copy database name to clipboard.</li>
    <li><kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>\</kbd>: To activate.</li>
  </ul>
</blockquote>

---

## Module Selector

Scans your repositories and lets you pick modules to install, update, or test. Selected modules are injected into Run Configurations via macros `$BTSModules$`, `$BTSModulesWithU$` and `$BTSModulesWithI$`. Simply create a new Run Configuration (e.g., `Update Modules`) and use the macro to target your selection.

You can also use the `$BTSAddonsPaths$` macro to define a custom addons path by adding `--addons-path=$BTSAddonsPaths$` to your Run Configuration.

![Animated demonstration of the Module Selector in Pycharm](https://raw.githubusercontent.com/TadeuszKarpinski/BTS-public/refs/heads/main/images/module_selector_2.gif)

* **Refresh** – Update the module list anytime. Auto-refreshes on startup.
* **Addons Paths** – Choose specific repositories to focus your search and utilize them with the `$BTSAddonsPaths$` macro.
* **Module Selection** – Pick the modules you need, then reference them in your Run Configuration using `$BTSModules$`, `$BTSModulesWithU$` or `$BTSModulesWithI$`.

<blockquote style="background-color: rgba(120,169,255,0.15); border-left: 5px solid #61c4ff; padding: 15px;">
  <b style="color: #3879b3;">💡 Pro Tip:</b>
  <ul style="margin-top: 10px; line-height: 1.6;">
    <li><kbd>Left-Click</kbd>: Start typing to find your modules.</li>
    <li><kbd>Middle-Click</kbd>: Fold.</li>
    <li><kbd>Right-Click</kbd>: Show context action.</li>
    <li><kbd>Ctrl</kbd> + <kbd>Click</kbd> or <kbd>Ctrl</kbd> + <kbd>Enter</kbd>: Jump to source.</li>
    <li><kbd>Alt</kbd> + <kbd>Click</kbd> or <kbd>Alt</kbd> + <kbd>Enter</kbd>: Copy module names to clipboard.</li>
    <li><kbd>_</kbd>: Show all modules.</li>
    <li><kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>Shift</kbd> + <kbd>\</kbd>: To activate.</li>
  </ul>
</blockquote>

---

## Test Selection

You can select either a unit test or an entire test class, then inject it into your Run Configuration using the `$BTSSelectedTest$` macro. Start it with `Test` Run Configuration.

![Odoo test selection context action for selecting a single test](https://raw.githubusercontent.com/TadeuszKarpinski/BTS-public/refs/heads/main/images/test_selection_2.png)

---

## Context Menu

**Braintec Exclusive**: <kbd>Right-click</kbd> any module to access a suite of specialized actions. Some operations may automatically trigger the installation of required `bt` plugins.

![Context menu showing Odoo-specific actions for Braintec](https://raw.githubusercontent.com/TadeuszKarpinski/BTS-public/refs/heads/main/images/bts_context_menu.png)

### Core Actions
* **Select/Unselect Module** – Quickly add or remove a module from your current selection.
* **Generate Readme** – Execute `bt utility generate-readme`.

### Code Analysis (Checks)
* **Quality & Compliance** – Run static analysis for code quality, verify licenses, and audit module dependencies.
* **Dependency Tree** – Visualize the full hierarchy of module requirements to identify potential conflicts.

### Automated Maintenance (Fixes)
* **Fix PO / Ruff** – Run `bt test checks-odoo-po` or `bt test ruff check` with the `--fix` and `--unsafe-fixes` flags.

### Odoo Testing
* **Run Tests** – Execute `bt test odoo` with options for specific modules, project-only, or non-project modules.
* **Coverage Report** – Generate a detailed coverage report during execution.
* **Cleanup** – Use the `Remove DB` option to delete the test database after the run.

### Translation Management
* **Export PO** – Run `bt utility bt-translation` for specified modules and databases.
* **Language Selection** – Define multiple languages (e.g., `de_DE`, `pl_PL`) using comma-separated values.

### Scaffolding
Quickly generate Odoo components using `bt utility scaffold`:
* **New Module** – Full module scaffolding.
* **Component Creators** – Dedicated actions for `Controllers`, `Migrations`, `Models`, `Views`, and `Wizards`.

---

## Run Configurations

Short, ready-to-use command examples for running Odoo with BTS. 

Keep in mind you don't always have to use every macro. For example, whether you need `--addons-path` depends on your project setup.

### 1. Install Modules

Enter a new database name under `Custom` and pick modules to **install** to initialize a fresh database with those modules.

```
$BTSModulesWithI$ $BTSDatabaseWithD$ --workers=0
```

<small><b>With addons paths:</b></small>

```
$BTSModulesWithI$ $BTSDatabaseWithD$ --workers=0 --addons-path=$BTSAddonsPaths$
```

![PyCharm Run Configuration for installing Odoo modules](https://raw.githubusercontent.com/TadeuszKarpinski/BTS-public/refs/heads/main/images/1_install_modules.png)

### 2. Start

Standard command to **start** Odoo with the selected database.

```
--dev=xml $BTSDatabaseWithD$
```

<small><b>With addons paths:</b></small>

```
--dev=xml $BTSDatabaseWithD$ --addons-path=$BTSAddonsPaths$
```

![PyCharm Run Configuration for starting the Odoo server](https://raw.githubusercontent.com/TadeuszKarpinski/BTS-public/refs/heads/main/images/2_start.png)

### 3. Update Modules

Select the modules to **update**, pick your database, and run. It’s the easiest way to apply your latest code changes to the database.

```
$BTSModulesWithU$ $BTSDatabaseWithD$ --i18n-overwrite --workers=0
```

<small><b>With addons paths:</b></small>

```
$BTSModulesWithU$ $BTSDatabaseWithD$ --i18n-overwrite --workers=0 --addons-path=$BTSAddonsPaths$aths$
```

![PyCharm Run Configuration for updating Odoo modules](https://raw.githubusercontent.com/TadeuszKarpinski/BTS-public/refs/heads/main/images/3_update_modules.png)

### 4. Test

Use this configuration to run a single test method or a single test class. 

`Right-Click` on a **test** method or class, select your database, and run the tests.

```
$BTSSelectedTest$ $BTSDatabaseWithD$ --workers=0 --stop-after-init
```

<small><b>With addons paths:</b></small>

```
$BTSSelectedTest$ $BTSDatabaseWithD$ --workers=0 --stop-after-init --addons-path=$BTSAddonsPaths$
```

![PyCharm Run Configuration for running single Odoo test](https://raw.githubusercontent.com/TadeuszKarpinski/BTS-public/refs/heads/main/images/4_test.png)

### 5. Test Modules

Select the modules to **test**, pick your database, and run. This will execute all tests in the selected modules.

```
--test-tags /$BTSModules$ $BTSDatabaseWithD$ --workers=0 --stop-after-init
```

<small><b>With addons paths:</b></small>

```
--test-tags /$BTSModules$ $BTSDatabaseWithD$ --workers=0 --stop-after-init --addons-path=$BTSAddonsPaths$
```

![PyCharm Run Configuration for running tests on specific Odoo modules](https://raw.githubusercontent.com/TadeuszKarpinski/BTS-public/refs/heads/main/images/5_test_modules.png)

---

## How to Setup

### 1. Configure your fetch database command.

* Open the **Database Selector** and select **Configure**.
* Navigate to **Fetch / Drop Databases**.
* Enter your fetch **command** in the designated field.
* **Tip**: Use the **test** function to ensure your command is working correctly.

![PyCharm interface for fetching the list of available Odoo databases](https://raw.githubusercontent.com/TadeuszKarpinski/BTS-public/refs/heads/main/images/db_fetch.png)

### 2. Auto-Generate BTS Run Configurations

* Open the **Database Selector** and click **Generate Run Configs**. This will automatically populate BTS recommended Run Configurations.
* Choose whether to include `--addons-path=$BTSAddonsPaths$` to your Run Configurations.
* Configuring the path to your `odoo.conf` is **optional**.

![Interface for automatically generating Odoo Run Configurations in PyCharm](https://raw.githubusercontent.com/TadeuszKarpinski/BTS-public/refs/heads/main/images/generate_run_configs.png)

### 3. Adjust the newly created Run Configurations.

* For example: Specify the path to your `odoo.conf` or adjust other project-specific settings like working directory.

### 4. Congratulations! You're ready to rock! 🎸

---

### Custom Integration

<blockquote style="background-color: rgba(255, 210, 64, 0.1); border-left: 5px solid #ffd240; padding: 15px;">
  <h2 style="color: #d46b08;">EXPLORE TOGETHER</h2> 
  <p style="font-size: 1.1em; font-weight: bold;">
    "Wanna see your workflow crack a smile?"
  </p>

  <p style="opacity: 0.9;">
    Need this plugin to work for your team or want custom actions built for your workflow? Let’s chat.
  </p>

  <p style="margin-top: 20px; font-weight: bold;">
    Tadeusz Jan Karpiński 🤙😎🤙
  </p>

  <p>
    <a href="mailto:tadeusz.karpinski@gmail.com" style="color: #58a6ff; text-decoration: none;">📧 tadeusz.karpinski@gmail.com</a>
    <span style="color: grey; margin: 0 10px;">|</span>
    <a href="https://bts-odoo-selector.com" style="color: #2ecc71; text-decoration: none;">🌐 bts-odoo-selector.com</a>
  </p>
</blockquote>

<!-- Plugin description end -->
