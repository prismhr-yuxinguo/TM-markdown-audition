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

- **AgileHR**: `AgileHR/Talent/Talent.Web/ClientApp/src/app/employees/employee-additional/phone-numbers/phone-numbers.component.html`
- **mocks-talent-ng**: `components-ng-shared/projects/mocks-talent-ng/src/app/employees/employee-additional/phone-numbers/phone-numbers.component.html`

### Differences in Markup Structure

#### AgileHR

- Contains a conditional rendering block `@if(isNew)` to display a message panel if the employee is new.
- Contains a `<message-panel>` component with attributes for title, content, state, and config.
- Contains a `<talent-grid>` component with various attributes for data handling and filtering.
- The `<talent-grid>` component includes:
  - `<e-columns>` with multiple `<e-column>` components for displaying data fields.
  - A custom template for the "Primary" column using `<ng-template>` and `<input-checkbox>`.
- Contains `<modal-base>` components for delete and new phone number modals with respective templates.
- The new phone number modal template contains a `<settings-table>` component with multiple `<settings-row>` components:
  - `<input-phone>` for phone number input.
  - `<input-dropdown>` for phone type input.
  - `<toggle-switch>` for primary number input.

#### mocks-talent-ng

- Contains a `<grid-filters>` component with attributes for center template and center header template.
- The center header template includes a custom toolbar with:
  - `<input-text>` for search input.
  - `<button-dropdown-grid>` for toolbar buttons.
- The center content template includes an `<ejs-grid>` component with various attributes for data handling and filtering.
- The `<ejs-grid>` component includes:
  - `<e-columns>` with multiple `<e-column>` components for displaying data fields.
  - A custom template for a dropdown button using `<ng-template>` and `<button-dropdown-grid>`.
- Contains `<modal-base>` components for delete, new, and edit phone number modals with respective templates.
- The new and edit phone number modal templates contain a `<settings-table>` component with multiple `<settings-row>` components:
  - `<input-phone>` for phone number input.
  - `<input-dropdown>` for phone type input.
  - `<toggle-switch>` for primary number input.

### Unique Markup Tags

#### AgileHR

- `message-panel`
- `talent-grid`
- `input-checkbox`

#### mocks-talent-ng

- `grid-filters`
- `input-text`
- `button-dropdown-grid`

### Differences in Markup Structure

- **AgileHR** uses a conditional rendering block `@if(isNew)` to display a message panel if the employee is new, while **mocks-talent-ng** does not.
- **AgileHR** uses a `<talent-grid>` component for data handling and filtering, while **mocks-talent-ng** uses a combination of `<grid-filters>` and `<ejs-grid>` components.
- **mocks-talent-ng** includes a custom toolbar with `<input-text>` and `<button-dropdown-grid>` components, which are not present in **AgileHR**.
- **AgileHR** includes a custom template for the "Primary" column using `<ng-template>` and `<input-checkbox>`, while **mocks-talent-ng** includes a custom template for a dropdown button using `<ng-template>` and `<button-dropdown-grid>`.

### Summary

The primary differences between the two files are the use of a conditional rendering block and a `<message-panel>` component in **AgileHR**, and the use of a custom toolbar with `<input-text>` and `<button-dropdown-grid>` components in **mocks-talent-ng**. Additionally, **AgileHR** uses a `<talent-grid>` component, while **mocks-talent-ng** uses a combination of `<grid-filters>` and `<ejs-grid>` components.

### Prod Screenshots

![Alt Text](/path/to/img.jpg)

### Mock Screenshots

![Alt Text](/path/to/img.jpg)

### URL

[link to the page in pro](https://www.example.com)

[link to the page in mock](https://www.example.com)
