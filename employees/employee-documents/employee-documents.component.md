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

- **AgileHR**: `AgileHR/Talent/Talent.Web/ClientApp/src/app/employees/employee-additional/employee-documents/employee-documents.component.html`
- **mocks-talent-ng**: `components-ng-shared/projects/mocks-talent-ng/src/app/employees/employee-additional/employee-documents/employee-documents.component.html`

### Differences in Markup Structure

#### AgileHR

- Contains a `<page-title>` component with `[title]="'Documents'"` attribute.
- Contains a `<div class="drawers">` section with nested `<div class="drawers__left">`, `<div class="drawers__center">`, and `<div class="drawers__right">` sections.
- The left drawer section includes:
  - A title with a `<button-base>` component for resetting filters.
  - A wrapper `<div class="drawers__left-wrapper">`.
- The center drawer section includes:
  - An `<ejs-tab>` component with multiple `<e-tabitem>` components for different tabs.
  - Each `<e-tabitem>` contains an `<ng-template>` with either `<upload-document>` or `<view-documents>` components.
- The right drawer section includes:
  - A close button with a `<button-base>` component.
  - A wrapper `<div class="drawers__right-wrapper">` containing:
    - An `<input-dropdown>` component for employee name selection.
    - Employee details including an image, name, title, company, department, division, office location, and supervisor email.

#### mocks-talent-ng

- Contains a `<page-title>` component with `[title]="'Documents'"` attribute.
- Contains a `<layout-drawers>` component with nested `<layout-drawer-center>` and `<layout-drawer-right>` sections.
- The center drawer section includes:
  - An `<ejs-tab>` component with multiple `<e-tabitem>` components for different tabs.
  - Each `<e-tabitem>` contains an `<ng-template>` with either `<upload-document>` or `<view-documents>` components.
- The right drawer section includes:
  - A `<layout-toolbox>` component with an `<app-ee-drawer>` component.

### Unique Markup Tags

#### AgileHR

- `div` (with class `drawers`, `drawers__left`, `drawers__center`, `drawers__right`, `drawers__left-title`, `drawers__left-wrapper`, `drawers__right-wrapper`)
- `button-base`
- `input-dropdown`
- `img` (for employee image)
- `span` (for employee details)

#### mocks-talent-ng

- `layout-drawers`
- `layout-drawer-center`
- `layout-drawer-right`
- `layout-toolbox`
- `app-ee-drawer`

### Differences in Markup Structure

- **AgileHR** uses a `<div>` based structure for the drawers, while **mocks-talent-ng** uses a `<layout-drawers>` component.
- **AgileHR** includes detailed employee information in the right drawer section, while **mocks-talent-ng** uses a `<layout-toolbox>` component with an `<app-ee-drawer>` component.
- **AgileHR** includes a reset filters button and an employee name dropdown in the left and right drawer sections, respectively, which are not present in **mocks-talent-ng**.

### Summary

The primary differences between the two files are the layout structures and the components used for displaying document-related information. **AgileHR** uses a `<div>` based structure with detailed employee information and additional controls in the drawers, while **mocks-talent-ng** uses a `<layout-drawers>` component with a simpler structure and an `<app-ee-drawer>` component in the right drawer section.

### Prod Screenshots

![Alt Text](/path/to/img.jpg)

### Mock Screenshots

![Alt Text](/path/to/img.jpg)

### URL

[link to the page in pro](https://www.example.com)

[link to the page in mock](https://www.example.com)
