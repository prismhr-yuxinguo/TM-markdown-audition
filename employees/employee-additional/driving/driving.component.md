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

- **AgileHR**: `AgileHR/Talent/Talent.Web/ClientApp/src/app/employees/employee-additional/driving/driving.component.html`
- **mocks-talent-ng**: `components-ng-shared/projects/mocks-talent-ng/src/app/employees/employee-additional/driving/driving.component.html`

### Differences in Markup Structure

#### AgileHR

- Contains an `<ejs-tab>` component with `id="tab_default"` and `headerPlacement="Left"` attributes.
- Contains multiple `<e-tabitem>` components with `[header]` attributes.
- Each `<e-tabitem>` contains an `<ng-template>` with a `#content` template reference variable.
- Each `<ng-template>` contains different components:
  - `<driving-records>` for the first tab.
  - `<driving-accidents>` for the second tab.

#### mocks-talent-ng

- Contains an `<ejs-tab>` component with `id="tab_default"` and `headerPlacement="Left"` attributes.
- Contains multiple `<e-tabitem>` components with `[header]` attributes.
- Each `<e-tabitem>` contains an `<ng-template>` with a `#content` template reference variable.
- Each `<ng-template>` contains different components:
  - `<driving-records>` for the first tab.
  - `<driving-accidents>` for the second tab.

### Unique Markup Tags

#### AgileHR

- None

#### mocks-talent-ng

- None

### Differences in Markup Structure

- Both files have identical markup structures with `<ejs-tab>`, `<e-tabitem>`, and `<ng-template>` components.
- There are no differences in the number or types of components used within the `<ng-template>` elements.

### Summary

The primary observation is that both files have identical markup structures and use the same components for managing driving records and driving accidents within the tabs.

### Prod Screenshots

![Alt Text](/path/to/img.jpg)

### Mock Screenshots

![Alt Text](/path/to/img.jpg)

### URL

[link to the page in pro](https://www.example.com)

[link to the page in mock](https://www.example.com)
