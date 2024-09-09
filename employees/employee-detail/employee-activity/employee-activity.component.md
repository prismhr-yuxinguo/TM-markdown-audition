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

- **AgileHR**: `AgileHR/Talent/Talent.Web/ClientApp/src/app/employees/employee-additional/activity/employee-activity.component.html`
- **mocks-talent-ng**: `components-ng-shared/projects/mocks-talent-ng/src/app/employees/employee-additional/activity/employee-activity.component.html`

### Differences in Markup Structure

#### AgileHR

- Contains a `<page-title>` component with `[title]="'Activity Log'"` attribute.
- Contains a `<talent-grid>` component with various attributes for data handling and filtering.
- The `<talent-grid>` component includes:
  - `<ng-template>` for filters with an `<input-dropdown>` component.
  - `<e-columns>` with multiple `<e-column>` components for displaying data fields.
- Contains `<modal-base>` components for delete and edit modals with respective templates.
- The delete modal template contains a `<div>` with a confirmation message.
- The edit modal template contains a `<div>` with a `<settings-table>` component and multiple `<settings-row>` components:
  - `<input-multiline>` for note input.
  - `<toggle-switch>` for sensitive input.

#### mocks-talent-ng

- Contains a `<page-title>` component with `[title]="'Activity Log'"` attribute.
- Contains a `<layout-drawers>` component with `<layout-drawer-center>` and `<layout-drawer-right>` sections.
- The `<layout-drawer-center>` section includes:
  - A `<grid-filters>` component with `<ng-template>` for center header and center content.
  - The center header template contains a custom toolbar with `<input-text>`, `<button-dropdown-grid>`, and `<button-new>` components.
  - The center content template contains an `<ejs-grid>` component with multiple `<e-column>` components for displaying data fields.
- The `<layout-drawer-right>` section includes a `<layout-toolbox>` component with an `<app-ee-drawer>` component.
- Contains a `<modal-base>` component for the new note modal with a respective template.

### Unique Markup Tags

#### AgileHR

- `talent-grid`
- `input-dropdown`
- `settings-table`
- `settings-row`
- `input-multiline`
- `toggle-switch`

#### mocks-talent-ng

- `layout-drawers`
- `layout-drawer-center`
- `layout-drawer-right`
- `grid-filters`
- `layout-toolbox`
- `app-ee-drawer`
- `button-new`

### Differences in Markup Structure

- **AgileHR** uses a `<talent-grid>` component for data handling and filtering, while **mocks-talent-ng** uses a combination of `<layout-drawers>`, `<grid-filters>`, and `<ejs-grid>` components.
- **AgileHR** includes `<settings-table>`, `<settings-row>`, `<input-multiline>`, and `<toggle-switch>` components within the edit modal, which are not present in **mocks-talent-ng**.
- **mocks-talent-ng** includes a custom toolbar with `<input-text>`, `<button-dropdown-grid>`, and `<button-new>` components, which are not present in **AgileHR**.

### Summary

The primary differences between the two files are the components used for data handling, filtering, and layout. **AgileHR** uses a `<talent-grid>` component, while **mocks-talent-ng** uses a combination of `<layout-drawers>`, `<grid-filters>`, and `<ejs-grid>` components. Additionally, **AgileHR** includes more detailed components within the edit modal, while **mocks-talent-ng** includes a custom toolbar with additional components.

### Prod Screenshots

![Alt Text](/path/to/img.jpg)

### Mock Screenshots

![Alt Text](/path/to/img.jpg)

### URL

[link to the page in pro](https://www.example.com)

[link to the page in mock](https://www.example.com)
