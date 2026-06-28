# Odoo Documentation Burmese Translation

This repository contains the Burmese/Myanmar locale files for the official Odoo documentation.

## Goal

The goal of this project is to develop and maintain Burmese/Myanmar `.po` locale files for Odoo documentation, because Odoo did not support Burmese/Myanmar documentation localization when this work was started.

These files can be used to preview the translated Odoo documentation locally.

## Requirements

Make sure you have the following tools installed:

- Git
- Python
- Make
- Sphinx documentation dependencies required by the Odoo documentation project

## Repository Structure

The Burmese locale files are already included in this repository:

```text
odoo_doc_mm_localization/
├── my/
│   └── LC_MESSAGES/
│       ├── index.po
│       ├── applications.po
│       ├── developer.po
│       └── ...
├── LICENSE
└── README.md
```

When using these files with the official Odoo documentation repository, copy the existing `my` directory into Odoo's `locale` directory.

## 1. Clone the Odoo Documentation Repository

Clone the official Odoo documentation repository:

```bash
git clone https://github.com/odoo/documentation.git
```

Go into the repository:

```bash
cd documentation
```

## 2. Add Burmese Language Support

Open the `conf.py` file.

Find the `language_names` dictionary around line 251 and add Burmese/Myanmar language support:

```python
language_names = {
    # existing languages...
    "my": "My",
}
```

`my` is the language code for Burmese/Myanmar.

## 3. Add the Existing Burmese Locale Files

From this repository, copy the existing `my` directory into the cloned Odoo documentation repository:

```bash
cp -r /path/to/odoo_doc_mm_localization/my locale/
```

After copying, the Odoo documentation repository should contain:

```text
locale/my/LC_MESSAGES/
```

Example structure:

```text
documentation/
├── conf.py
├── locale/
│   └── my/
│       └── LC_MESSAGES/
│           ├── index.po
│           ├── applications.po
│           ├── developer.po
│           └── ...
```

## 4. Build the Documentation

Build the Odoo documentation using the Burmese language code:

```bash
make html CURRENT_LANG=my
```

This command generates the translated HTML documentation.

## 5. Open the Translated Documentation

After the build is completed, open the generated `index.html` file in your browser.

The file is usually located inside the `_build` directory:

```text
_build/html/index.html
```

On Linux:

```bash
xdg-open _build/html/index.html
```

On macOS:

```bash
open _build/html/index.html
```

On Windows:

```powershell
start _build/html/index.html
```

You should now be able to see the Odoo documentation in Burmese/Myanmar locally.

## License and Attribution

This repository is an unofficial Burmese/Myanmar translation locale package for the Odoo documentation.

The original Odoo documentation is copyright Odoo S.A. and contributors, and is licensed under the Creative Commons Attribution-ShareAlike 4.0 International License (`CC-BY-SA-4.0`).

Because these `.po` files are based on the official Odoo documentation source strings and include Burmese/Myanmar translations, this repository follows the same `CC-BY-SA-4.0` license. See the `LICENSE` file for details.

Odoo is a trademark of Odoo S.A. This repository is not officially endorsed by Odoo S.A. unless it is accepted into the official Odoo documentation or translation workflow.
