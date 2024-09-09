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

- **AgileHR**: `AgileHR/Talent/Talent.Web/ClientApp/src/app/employees/employee-additional/dependents/new-dependent/new-dependent.component.html`
- **mocks-talent-ng**: `components-ng-shared/projects/mocks-talent-ng/src/app/employees/employee-additional/dependents/new-dependent/new-dependent.component.html`

### Differences in Markup Structure

#### AgileHR

- Contains a `<settings-table>` component with `[settingsTitle]` and `[formGroup]` attributes.
- Contains multiple `<settings-row>` components with `[title]`, `[description]`, and `[required]` attributes.
- Each `<settings-row>` contains different input components:
  - `<input-text>` for first name, middle name, last name, social security number, address 1, address 2, and city inputs.
  - `<input-dropdown>` for relationship, gender, and state inputs.
  - `<input-datepicker>` for date of birth input.
  - `<toggle-switch>` for copying address from employee.
  - `<input-phone>` for ZIP code and home phone inputs.

#### mocks-talent-ng

- Contains a `<settings-table>` component with `[settingsTitle]` and `[formGroup]` attributes.
- Contains multiple `<settings-row>` components with `[title]`, `[description]`, and `[required]` attributes.
- Each `<settings-row>` contains different input components:
  - `<input-text>` for first name, middle name, last name, social security number, address 1, address 2, and city inputs.
  - `<input-dropdown>` for relationship, gender, and state inputs.
  - `<input-datepicker>` for date of birth input.
  - `<toggle-switch>` for copying address from employee.
  - `<input-phone>` for ZIP code and home phone inputs.

### Unique Markup Tags

#### AgileHR

- None

#### mocks-talent-ng

- None

### Differences in Markup Structure

- Both files have identical markup structures with `<settings-table>`, `<settings-row>`, `<input-text>`, `<input-dropdown>`, `<input-datepicker>`, `<toggle-switch>`, and `<input-phone>` components.
- There are no differences in the number or types of input components used within the `<settings-row>` elements.

### Summary

The primary observation is that both files have identical markup structures and use the same components for first name, middle name, last name, relationship, social security number, date of birth, gender, address 1, address 2, city, state, ZIP code, and home phone inputs.

### Prod Screenshots

![Alt Text](/path/to/img.jpg)

### Mock Screenshots

![Alt Text](/path/to/img.jpg)

### URL

[link to the page in pro](https://www.example.com)

[link to the page in mock](https://www.example.com)
