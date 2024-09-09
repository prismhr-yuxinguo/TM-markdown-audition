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

- **AgileHR**: `AgileHR/Talent/Talent.Web/ClientApp/src/app/employees/employee-additional/training/new-talent/new-talent.component.html`
- **mocks-talent-ng**: `components-ng-shared/projects/mocks-talent-ng/src/app/employees/employee-additional/training/new-talent/new-talent.component.html`

### Differences in Markup Structure

#### AgileHR

- Contains a `<settings-table>` component with `[settingsTitle]` and `[formGroup]` attributes.
- Contains multiple `<settings-row>` components with `[title]`, `[description]`, and `[required]` attributes.
- Each `<settings-row>` contains different input components:
  - `<input-dropdown>` for training category and training course inputs.
  - `<input-datepicker>` for date completed, course start date, and course end date inputs.
  - `<input-text>` for hours completed, total course hours, and hours remaining inputs.
  - `<input-multiline>` for course description input.

#### mocks-talent-ng

- Contains a `<settings-table>` component with `[settingsTitle]` and `[formGroup]` attributes.
- Contains multiple `<settings-row>` components with `[title]`, `[description]`, and `[required]` attributes.
- Each `<settings-row>` contains different input components:
  - `<input-dropdown>` for training category and training course inputs.
  - `<input-datepicker>` for date completed, course start date, and course end date inputs.
  - `<input-text>` for hours completed, total course hours, and hours remaining inputs.
  - `<input-multiline>` for course description input.

### Unique Markup Tags

#### AgileHR

- None

#### mocks-talent-ng

- None

### Differences in Markup Structure

- Both files have identical markup structures with `<settings-table>`, `<settings-row>`, `<input-dropdown>`, `<input-datepicker>`, `<input-text>`, and `<input-multiline>` components.
- There are no differences in the number or types of input components used within the `<settings-row>` elements.

### Summary

The primary observation is that both files have identical markup structures and use the same components for training category, training course, date completed, course start date, course end date, hours completed, total course hours, hours remaining, and course description inputs.

### Prod Screenshots

![Alt Text](/path/to/img.jpg)

### Mock Screenshots

![Alt Text](/path/to/img.jpg)

### URL

[link to the page in pro](https://www.example.com)

[link to the page in mock](https://www.example.com)
