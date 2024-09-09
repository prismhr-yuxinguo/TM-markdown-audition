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

- **AgileHR**: `AgileHR/Talent/Talent.Web/ClientApp/src/app/employees/employee-additional/driving-accidents/new-driving-accident/new-driving-accident.component.html`
- **mocks-talent-ng**: `components-ng-shared/projects/mocks-talent-ng/src/app/employees/employee-additional/driving-accidents/new-driving-accident/new-driving-accident.component.html`

### Differences in Markup Structure

#### AgileHR

- Contains a `<settings-table>` component with `[settingsTitle]` and `[formGroup]` attributes.
- Contains multiple `<settings-row>` components with `[title]`, `[description]`, and `[required]` attributes.
- Each `<settings-row>` contains different input components:
  - `<input-datepicker>` for date input.
  - `<toggle-switch>` for employee at fault, injury accident, and fatality accident inputs.
  - `<input-multiline>` for nature of accident input.

#### mocks-talent-ng

- Contains a `<settings-table>` component with `[settingsTitle]` and `[formGroup]` attributes.
- Contains multiple `<settings-row>` components with `[title]`, `[description]`, and `[required]` attributes.
- Each `<settings-row>` contains different input components:
  - `<input-datepicker>` for date input.
  - `<toggle-switch>` for employee at fault, injury accident, and fatality accident inputs.
  - `<input-multiline>` for nature of accident input.

### Unique Markup Tags

#### AgileHR

- None

#### mocks-talent-ng

- None

### Differences in Markup Structure

- Both files have identical markup structures with `<settings-table>`, `<settings-row>`, `<input-datepicker>`, `<toggle-switch>`, and `<input-multiline>` components.
- There are no differences in the number or types of input components used within the `<settings-row>` elements.

### Summary

The primary observation is that both files have identical markup structures and use the same components for date, employee at fault, injury accident, fatality accident, and nature of accident inputs.

### Prod Screenshots

![Alt Text](/path/to/img.jpg)

### Mock Screenshots

![Alt Text](/path/to/img.jpg)

### URL

[link to the page in pro](https://www.example.com)

[link to the page in mock](https://www.example.com)
