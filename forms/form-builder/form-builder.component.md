## File Comparison Report

## Table of Contents

- [File Paths](#file-paths)
- [Differences in Markup Structure](#differences-in-markup-structure)
  - [AgileHR](#agilehr)
  - [mocks-talent-ng](#mocks-talent-ng)
- [Unique Markup Tags](#unique-markup-tags)
  - [AgileHR](#agilehr-1)
  - [mocks-talent-ng](#mocks-talent-ng-1)
- [Summary](#summary)
- [Prod Screenshots](#prod-screenshots)
- [Mock Screenshots](#mock-screenshots)
- [URL](#url)

### File Paths

- **AgileHR**: `AgileHR/Talent/Talent.Web/ClientApp/src/app/employees/employee-additional/form-builder/form-builder.component.html`
- **mocks-talent-ng**: `components-ng-shared/projects/mocks-talent-ng/src/app/employees/employee-additional/form-builder/form-builder.component.html`

### Differences in Markup Structure

#### AgileHR

- Contains a `<page-title>` component with `[title]="'Form Builder'"` attribute.
- Contains an `<ejs-tab>` component with `id="adaptiveTab"` and `overflowMode="Popup"` attributes.
- The first tab item includes:
  - A `<settings-table>` component with multiple `<settings-row>` components for form details:
    - `<settings-row>` for "Form Name" with an `<input-text>` component.
    - `<settings-row>` for "Form Type" with an `<input-dropdown>` component.
    - `<settings-row>` for "View" with an `<input-dropdown>` component.
    - `<settings-row>` for "Auto Include Globally" with a `<toggle-switch>` component.
    - `<settings-row>` for "Effective Date" with an `<input-datepicker>` component.
- The second tab item includes:
  - An `<app-fd-editor>` component.

#### mocks-talent-ng

- Contains a `<page-title>` component with `[title]="'Form Builder'"` attribute.
- Contains an `<ejs-tab>` component with `id="adaptiveTab"` and `overflowMode="Popup"` attributes.
- The first tab item includes:
  - A `<settings-table>` component with multiple `<settings-row>` components for form details:
    - `<settings-row>` for "Form Name" with an `<input-text>` component.
    - `<settings-row>` for "Form Type" with an `<input-dropdown>` component.
    - `<settings-row>` for "View" with an `<input-dropdown>` component.
    - `<settings-row>` for "Auto Include Globally" with a `<toggle-switch>` component.
    - `<settings-row>` for "Effective Date" with an `<input-datepicker>` component.
- The second tab item includes:
  - An `<app-fd-editor>` component.

### Unique Markup Tags

#### AgileHR

- None

#### mocks-talent-ng

- None

### Differences in Markup Structure

- The primary difference between the two files is the formatting of the `[description]` attribute in the `<settings-row>` components:
  - **AgileHR**: `[description]=""`
  - **mocks-talent-ng**: `[description]="''"`

### Summary

The primary difference between the two files is the formatting of the `[description]` attribute in the `<settings-row>` components. Both files contain identical structures for the form builder, including the page title, tab items, and settings table with various input components.

### Prod Screenshots

![Alt Text](/path/to/img.jpg)

### Mock Screenshots

![Alt Text](/path/to/img.jpg)

### URL

[link to the page in pro](https://www.example.com)

[link to the page in mock](https://www.example.com)
