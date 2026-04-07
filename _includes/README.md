<!-- Plugin description -->

**BTS: Odoo Selector Pro** 

Your **Odoo** command center for **PyCharm**. Effortlessly switch between **databases** and **modules** without touching complex settings. Run, test, and develop faster!

- **Switch DBs in One Click:** Pick a database, and it’s updated in your config instantly.
- **Select & Run Modules:** Search and pick modules to install, update, or test in seconds.
- **Easily create Run Configurations:** Get all BTS-recommended configurations with just a few clicks.

<blockquote style="background-color: rgba(76, 175, 80, 0.1); border-left: 5px solid #61c4ff; padding: 15px;">
  <b style="color: #4CAF50;">✅ Quick 3-Step Setup:</b>
  <ul style="margin-top: 10px; line-height: 1.6;">
    <li>Configure you fetch database command.</li>
    <li>Create Recommended BTS Run Configurations.</li>
    <li>Adjust the newly created Run Configurations.</li>
  </ul>
  Follow the guided instructions in the <b>How to Setup</b> section.
</blockquote>

## Official Music Video

[![Official Music Video](https://raw.githubusercontent.com/TadeuszKarpinski/BTS-public/refs/heads/main/images/BTS.jpg)](https://odoo.fail/bts/video)

## Amazing Features
* [Database Selector](#database-selector)
* [Module Selector](#module-selector)
* [Test Selection](#test-selection)
* [Context Menu](#context-menu)
* [Run Configuration Examples](#run-configuration-examples)
* [How to Setup](#how-to-setup)
* [Custom Integration](#custom-integration)

## Links
* [Website & Documentation](https://bts-odoo-selector.com/)
* [JetBrains Marketplace](https://plugins.jetbrains.com/plugin/26426-bts-odoo-selector-pro)

## Database Selector

Updates `db_name` in `odoo.conf` to the database you picked. Alternatively, use macros `$BTSDatabase$` and `$BTSDatabaseWithD$` directly in your Run Configuration.

<img src="https://raw.githubusercontent.com/TadeuszKarpinski/BTS-public/refs/heads/main/images/db_selector.gif"/>

* **Refresh** – Automatically refreshes the database list when PyCharm starts or when the `odoo.conf` path changes. Manual refresh is required after creating, deleting, or copying databases.
* **Database** – Pick a database to update `db_name` in `odoo.conf` automatically, or use it in your Run Configuration with macros like `$BTSDatabase$` or `$BTSDatabaseWithD$`.
  * `Delete` – Automatically configured for Braintec, PwC, and Ventortech.
  * `Duplicate` / `Rename` – Braintec exclusive.
* **All Databases** – Picking this option sets `db_name` to `False` in your `odoo.conf` file.
* **Custom** – Manually type in a `db_name` to be saved to your `odoo.conf`. This allows you to set a new name and run your install config to spin up a fresh database.
* **Configure** – Advanced settings and automation:
  * `Fetch / Drop Databases` – Commands to fetch or delete databases (Auto-configured for partner environments).
  * `Path to odoo.conf` – Set a custom path for your configuration file (Auto-configured for Braintec, PwC, and VentorTech).
  * `Predefined Databases` – Set up your own list of go-to database names.

<blockquote style="background-color: rgba(120,169,255,0.15); border-left: 5px solid #61c4ff; padding: 15px;">
  <b style="color: #3879b3;">💡 Pro Tip:</b>
  <ul style="margin-top: 10px; line-height: 1.6;">
    <li><kbd>Left-Click</kbd> - start typing to fond your database.</li>
    <li><kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>\</kbd> - to activate.</li>
    <li><kbd>Alt</kbd> + <kbd>Click</kbd> or <kbd>Alt</kbd> + <kbd>Enter</kbd> – Copy name to clipboard.</li>
    <li><kbd>Middle-Click</kbd> to fold.</li>
  </ul>
</blockquote>

---

## Module Selector

Scans your repositories and lets you pick modules to install, update, or test. Selected modules are injected into Run Configurations via macros `$BTSModules$` and `$BTSModulesWithU$`. Simply create a new Run Configuration (e.g., Update) and use the macro to target your selection.

You can also use the `$BTSAddonsPaths$` macro to define a custom addons path by adding `--addons-path=$BTSAddonsPaths$` to your Run Configuration.

<img src="https://raw.githubusercontent.com/TadeuszKarpinski/BTS-public/refs/heads/main/images/module_selector.gif"/>

* **Refresh** – Refresh the module list on demand.
* **Addons Paths** – Choose specific repositories to focus your search and utilize them with the `$BTSAddonsPaths$` macro.
* **Module Selection** – Pick the modules you need, then reference them in your Run Configuration using `$BTSModules$` or `$BTSModulesWithU$`.

<blockquote style="background-color: rgba(120,169,255,0.15); border-left: 5px solid #61c4ff; padding: 15px;">
  <b style="color: #3879b3;">💡 Pro Tip:</b>
  <ul style="margin-top: 10px; line-height: 1.6;">
    <li><kbd>Left-Click</kbd> - start typing to fond your modules.</li>
    <li><kbd>Middle-Click</kbd> to fold.</li>
    <li><kbd>Right-Click</kbd> Show context action.</li>
    <li><kbd>Ctrl</kbd> + <kbd>Enter</kbd> or <kbd>Ctrl</kbd> + <kbd>Click</kbd> - jump to source.</li>
    <li><kbd>Alt</kbd> + <kbd>Click</kbd> or <kbd>Alt</kbd> + <kbd>Enter</kbd> – Copy module names to clipboard.</li>
    <li><kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>Shift</kbd> + <kbd>\</kbd> - to activate.</li>
    <li><kbd>_</kbd> - to search in all modules.</li>
  </ul>
</blockquote>

---

## Test Selection

A streamlined way to target specific tests. You can select either a unit test or an entire test class, then inject it into your Run Configuration using the `$BTSSelectedTest$` macro.

<img src="https://raw.githubusercontent.com/TadeuszKarpinski/BTS-public/refs/heads/main/images/test_selection.png"/>

* **Granular Control** – Toggle between individual test methods and full classes.
* **Macro Integration** – Use `$BTSSelectedTest$` to automate test execution across different environments.

---

## Context Menu - Braintec Exclusive

<kbd>Right-click</kbd> any module to access a suite of specialized actions. Some operations may automatically trigger the installation of required `bt` plugins.

<img src="https://raw.githubusercontent.com/TadeuszKarpinski/BTS-public/refs/heads/main/images/bts_context_menu.png"/>

### Core Actions
* **Select/Unselect Module** – Quickly add or remove a module from your current selection.
* **Generate Readme** – Execute `bt utility generate-readme <modules>`.

### Quality & Compliance
* **Check Quality** – Run code quality tests via `bt test code quality`.
* **Fix PO / Ruff** – Run `bt test checks-odoo-po` or `bt test ruff check` with the `--fix` flag.
* **Dependencies & Licenses** – Optimize module dependencies or verify licenses using `bt utility`.

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

## Run Configuration Examples

Keep in mind you don't always have to use every macro. For example, whether you need `--addons-path` depends on your project setup.

### 1. Install Modules

```
-i $BTSModules$ $BTSDatabaseWithD$
```

<small><b>With addons paths:</b></small>

```
-i $BTSModules$ $BTSDatabaseWithD$ --addons-path=$BTSAddonsPaths$
```

<img src="https://raw.githubusercontent.com/TadeuszKarpinski/BTS-public/refs/heads/main/images/1_install_modules.png"/>

### 2. Start

```
--dev=xml $BTSDatabaseWithD$
```

<small><b>With addons paths:</b></small>

```
--dev=xml $BTSDatabaseWithD$ --addons-path=$BTSAddonsPaths$
```

<img src="https://raw.githubusercontent.com/TadeuszKarpinski/BTS-public/refs/heads/main/images/2_start.png"/>


### 3. Update Modules

```
-u $BTSModules$ $BTSDatabaseWithD$ --i18n-overwrite
```

<small><b>With addons paths:</b></small>

```
-u $BTSModules$ $BTSDatabaseWithD$ --i18n-overwrite --addons-path=$BTSAddonsPaths$aths$
```


<img src="https://raw.githubusercontent.com/TadeuszKarpinski/BTS-public/refs/heads/main/images/3_update_modules.png"/>

### 4. Test

```
$BTSSelectedTest$ $BTSDatabaseWithD$ --workers=0 --stop-after-init
```

<small><b>With addons paths:</b></small>

```
$BTSSelectedTest$ $BTSDatabaseWithD$ --workers=0 --stop-after-init --addons-path=$BTSAddonsPaths$
```

<img src="https://raw.githubusercontent.com/TadeuszKarpinski/BTS-public/refs/heads/main/images/4_test.png"/>

### 5. Test Modules

```
--test-tags /$BTSModules$ $BTSDatabaseWithD$ --workers=0 --stop-after-init
```

<small><b>With addons paths:</b></small>

```
--test-tags /$BTSModules$ $BTSDatabaseWithD$ --workers=0 --stop-after-init --addons-path=$BTSAddonsPaths$
```

<img src="https://raw.githubusercontent.com/TadeuszKarpinski/BTS-public/refs/heads/main/images/5_test_modules.png"/>

---

## How to Setup

### 1. Configure you fetch database command.

* Open the **Database Selector** and select **Configure**.
* Navigate to **Fetch / Drop Databases**.
* Enter your fetch **command** in the designated field.
* **Tip**: Use the test function to ensure your command is working correctly.

<img src="https://raw.githubusercontent.com/TadeuszKarpinski/BTS-public/refs/heads/main/images/db_fetch.png"/>

### 2. Create Recommended BTS Run Configurations.

* Open the **Database Selector** and click **Add BTS Run Configs**.
* Choose whether to add `--addons-path=$BTSAddonsPaths$` to your Run Configurations based on your specific project setup.
* Configuring the path to your `odoo.conf` is **optional**.

<img src="https://raw.githubusercontent.com/TadeuszKarpinski/BTS-public/refs/heads/main/images/add_addons_path.png"/>

### 3. Adjust the newly created Run Configurations.

* For example: Specify the path to your `odoo.conf` or adjust other project-specific settings.

### 4. Congratulations! You're ready to rock!

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
