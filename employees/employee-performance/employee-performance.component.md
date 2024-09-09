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
- **AgileHR**: `AgileHR/Talent/Talent.Web/ClientApp/src/app/employees/employee-performance/employee-performance.component.html`
- **mocks-talent-ng**: `components-ng-shared/projects/mocks-talent-ng/src/app/employees/employee-performance/employee-performance.component.html`

### Differences in Markup Structure

#### AgileHR
- Contains a `<page-title>` component with `[title]="'Performance'"` attribute.
- Contains a `<div class="drawers">` section with nested `<div class="drawers__left">`, `<div class="drawers__center">`, and `<div class="drawers__right">` sections.
- The left drawer section includes:
  - A title with a `<button-base>` component for resetting filters.
  - A wrapper `<div class="drawers__left-wrapper">`.
- The center drawer section includes:
  - An `<ejs-tab>` component with multiple `<e-tabitem>` components for different tabs.
  - Each `<e-tabitem>` contains an `<ng-template>` with either `<app-eep-deets>` or a custom grid filter section.
  - The custom grid filter section includes:
    - A `<div class="grid-filters">` section with nested `<div class="grid-filters__left">`, `<div class="grid-filters__center">`, and `<div class="grid-filters__right">` sections.
    - The left section includes a title with a `<button-base>` component for closing filters and a wrapper `<div class="grid-filters__left-wrapper">`.
    - The center section includes an `<ejs-grid>` component with a custom toolbar template and multiple columns.
    - The toolbar template includes a search bar and a button for toggling search filters.
    - The right section is empty.
- The right drawer section includes:
  - A close button with a `<button-base>` component.
  - A wrapper `<div class="drawers__right-wrapper">` containing:
    - An `<input-dropdown>` component for employee name selection.
    - Employee details including an image, name, title, company, department, division, office location, and supervisor email.

#### mocks-talent-ng
- Contains a `<page-title>` component with `[title]="'Performance'"` attribute.
- Contains a `<layout-drawers>` component with nested `<layout-drawer-center>` and `<layout-drawer-right>` sections.
- The center drawer section includes:
  - An `<ejs-tab>` component with multiple `<e-tabitem>` components for different tabs.
  - Each `<e-tabitem>` contains an `<ng-template>` with either `<app-eep-deets>` or a custom grid filter section.
  - The custom grid filter section includes:
    - A `<grid-filters>` component with `centerTemplate` and `centerHeaderTemplate` attributes.
    - The center header template includes a custom toolbar with a search bar.
    - The center content template includes an `<ejs-grid>` component with attributes for adaptive UI, vertical row rendering, and paging.
    - Multiple columns including a checkbox column, appraiser column, weight column with inline editing, and confidential column with a toggle switch.
- The right drawer section includes:
  - A `<layout-toolbox>` component with an `<app-ee-drawer>` component.

### Unique Markup Tags

#### AgileHR
- `div` (with class `drawers`, `drawers__left`, `drawers__center`, `drawers__right`, `drawers__left-title`, `drawers__left-wrapper`, `grid-filters`, `grid-filters__left`, `grid-filters__center`, `grid-filters__right`, `grid-filters__left-title`, `grid-filters__left-wrapper`, `drawers__right-wrapper`)
- `button-base` (for resetting filters, closing filters, toggling search filters, and closing the drawer)
- `input-dropdown` (for employee name selection)
- `img` (for employee image)
- `span` (for employee details)

#### mocks-talent-ng
- `layout-drawers`
- `layout-drawer-center`
- `layout-drawer-right`
- `grid-filters`
- `centerTemplate`
- `centerHeaderTemplate`
- `layout-toolbox`
- `app-ee-drawer`

### Differences in Markup Structure
- **AgileHR** uses a `<div>` based structure for the drawers and grid filters, while **mocks-talent-ng** uses a `<layout-drawers>` component with `centerTemplate` and `centerHeaderTemplate` attributes for custom grid filters.
- **AgileHR** includes detailed employee information in the right drawer section, while **mocks-talent-ng** uses a `<layout-toolbox>` component with an `<app-ee-drawer>` component.
- **mocks-talent-ng** includes additional attributes for adaptive UI and vertical row rendering in the `<ejs-grid>` component, which are not present in **AgileHR**.

### Summary
The primary differences between the two files are the layout structures and the components used for displaying grid filters and employee information. **AgileHR** uses a `<div>` based structure with detailed employee information and additional controls in the drawers, while **mocks-talent-ng** uses a `<layout-drawers>` component with a simpler structure and an `<app-ee-drawer>` component in the right drawer section. Additionally, **mocks-talent-ng** includes attributes for adaptive UI and vertical row rendering in the `<ejs-grid>` component.

### Prod Screenshots

![Alt Text](/path/to/img.jpg)

### Mock Screenshots

![Alt Text](/path/to/img.jpg)

### URL

[link to the page in pro](https://www.example.com)

[link to the page in mock](https://www.example.com)