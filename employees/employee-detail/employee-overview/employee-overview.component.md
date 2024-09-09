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

- **AgileHR**: `AgileHR/Talent/Talent.Web/ClientApp/src/app/employees/employee-overview/employee-overview.component.html`
- **mocks-talent-ng**: `components-ng-shared/projects/mocks-talent-ng/src/app/employees/employee-overview/employee-overview.component.html`

### Differences in Markup Structure

#### AgileHR

- Contains a `<page-title>` component with `[title]="'Employee Information'"` attribute.
- Contains a `<div class="drawers">` section with nested `<div class="drawers__left">` and `<div class="drawers__center">` sections.
- The left drawer section includes:
  - A title with a `<button-base>` component for resetting filters.
  - A wrapper `<div class="drawers__left-wrapper">`.
- The center drawer section includes:
  - A `<navigation-tab>` component.
  - A `<router-outlet>` component for dynamic content.

#### mocks-talent-ng

- Contains a `<page-title>` component with `[title]="'Employee Information'"` attribute.
- Contains a `<layout-drawers>` component with nested `<layout-drawer-center>` and `<layout-drawer-right>` sections.
- The center drawer section includes:
  - An `<ejs-tab>` component with multiple `<e-tabitem>` components for different tabs.
  - Each `<e-tabitem>` contains an `<ng-template>` with various components such as `<personal-information>`, `<phone-numbers>`, `<sensitive-information>`, `<emergency-contacts>`, `<employment-information>`, `<social-media>`, and `<employment-history>`.
- The right drawer section includes:
  - A `<layout-toolbox>` component with an `<app-ee-drawer>` component.

### Unique Markup Tags

#### AgileHR

- `div` (with class `drawers`, `drawers__left`, `drawers__center`, `drawers__left-title`, `drawers__left-wrapper`)
- `button-base`
- `navigation-tab`
- `router-outlet`

#### mocks-talent-ng

- `layout-drawers`
- `layout-drawer-center`
- `layout-drawer-right`
- `ejs-tab`
- `e-tabitem`
- `ng-template`
- `layout-toolbox`
- `app-ee-drawer`

### Differences in Markup Structure

- **AgileHR** uses a `<div>` based structure for the drawers, while **mocks-talent-ng** uses a `<layout-drawers>` component.
- **AgileHR** includes a `<navigation-tab>` and `<router-outlet>` for dynamic content, while **mocks-talent-ng** uses an `<ejs-tab>` component with multiple tabs for different sections.
- **mocks-talent-ng** includes a right drawer section with a `<layout-toolbox>` and `<app-ee-drawer>`, which are not present in **AgileHR**.

### Summary

The primary differences between the two files are the layout structures and the components used for displaying employee information. **AgileHR** uses a `<div>` based structure with a `<navigation-tab>` and `<router-outlet>`, while **mocks-talent-ng** uses a `<layout-drawers>` component with an `<ejs-tab>` for multiple tabs and a right drawer section with additional components.

### Prod Screenshots

![Alt Text](/path/to/img.jpg)

### Mock Screenshots

![Alt Text](/path/to/img.jpg)

### URL

[link to the page in pro](https://www.example.com)

[link to the page in mock](https://www.example.com)
