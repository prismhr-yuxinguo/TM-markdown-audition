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

- **AgileHR**: `AgileHR/Talent/Talent.Web/ClientApp/src/app/employees/employee-additional/employee-additional.component.html`
- **mocks-talent-ng**: `components-ng-shared/projects/mocks-talent-ng/src/app/employees/employee-additional/employee-additional.component.html`

### Differences in Markup Structure

#### AgileHR

- Contains a `<page-title>` component with `[title]="'Additional Information'"` attribute.
- Contains a `<div class="e-main-content__close tab--h">` section with a `<button-base>` component for toggling the sidebar.
- Contains an `<ejs-sidebar>` component with various attributes for the right sidebar.
- The sidebar contains a `<button-base>` component for closing the drawer and an `<employee-sidebar>` component.
- Contains a `<div class="e-main-content">` section with an `<ejs-tab>` component.
- The `<ejs-tab>` component contains multiple `<e-tabitem>` components with `[header]` attributes and `<ng-template>` elements for content.
  - `<dependents>`, `<assets>`, `<compensation>`, `<driving>`, and `<education>` components are used within the tabs.

#### mocks-talent-ng

- Contains a `<page-title>` component with `[title]="'Additional Information'"` attribute.
- Contains a `<layout-drawers>` component with `<layout-drawer-center>` and `<layout-drawer-right>` sections.
- The `<layout-drawer-center>` section contains an `<ejs-tab>` component.
- The `<ejs-tab>` component contains multiple `<e-tabitem>` components with `[header]` attributes and `<ng-template>` elements for content.
  - `<dependents>`, `<assets>`, `<compensation>`, `<driving>`, and `<education>` components are used within the tabs.
- The `<layout-drawer-right>` section contains a `<layout-toolbox>` component with an `<app-ee-drawer>` component.

### Unique Markup Tags

#### AgileHR

- `div` (with class `e-main-content__close tab--h`, `e-main-content`)
- `button-base`
- `ejs-sidebar`
- `employee-sidebar`

#### mocks-talent-ng

- `layout-drawers`
- `layout-drawer-center`
- `layout-drawer-right`
- `layout-toolbox`
- `app-ee-drawer`

### Differences in Markup Structure

- **AgileHR** uses a combination of `<div>`, `<button-base>`, and `<ejs-sidebar>` components for the sidebar and main content layout.
- **mocks-talent-ng** uses a `<layout-drawers>` component with `<layout-drawer-center>` and `<layout-drawer-right>` sections for the layout.
- **AgileHR** includes an `<employee-sidebar>` component within the sidebar, while **mocks-talent-ng** includes an `<app-ee-drawer>` component within the right drawer.

### Summary

The primary differences between the two files are the layout structures and the components used for the sidebar and main content. **AgileHR** uses `<div>`, `<button-base>`, and `<ejs-sidebar>` components, while **mocks-talent-ng** uses a `<layout-drawers>` component with `<layout-drawer-center>` and `<layout-drawer-right>` sections. Additionally, **AgileHR** includes an `<employee-sidebar>` component, whereas **mocks-talent-ng** includes an `<app-ee-drawer>` component.

### Prod Screenshots

![Alt Text](/path/to/img.jpg)

### Mock Screenshots

![Alt Text](/path/to/img.jpg)

### URL

[link to the page in pro](https://www.example.com)

[link to the page in mock](https://www.example.com)
