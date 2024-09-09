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

- **AgileHR**: `AgileHR/Talent/Talent.Web/ClientApp/src/app/employees/employee-additional/employees/employees.component.html`
- **mocks-talent-ng**: `components-ng-shared/projects/mocks-talent-ng/src/app/employees/employee-additional/employees/employees.component.html`

### Differences in Markup Structure

#### AgileHR

- Contains a `<page-title>` component with `[title]="'Employees'"` attribute.
- Contains a `<talent-grid>` component with various attributes and event bindings:
  - `[allowNew]="hasCreate"`
  - `[allowRowSelect]="hasActions"`
  - `(applyFilters)="applyFilters($event)"`
  - `(bulk)="bulk($event)"`
  - `[bulkActionTooltip]="bulkActionTooltip"`
  - `[bulkOptions]="bulkOptions"`
  - `[data]="data"`
  - `exportFileName="Employees"`
  - `[filters]="filters"`
  - `[filtersForm]="filtersForm"`
  - `friendlyName="Employee"`
  - `[initializing]="initializing"`
  - `[loading]="loading"`
  - `(rowSelected)="rowSelected()"`
  - `[searchFields]="searchFields"`
  - `(selected)="selected($event)"`
  - `[selectActionTooltip]="selectActionTooltip"`
  - `[selectOptions]="getSelectOptions"`
  - `(sortDir)="sortDirChanged($event)"`
  - `idProperty="typeId"`
- Contains a `<ng-template #filtersTemplate>` with multiple `<input-dropdown-multi>` and `<input-dropdown>` components for filtering.
- Contains multiple `<e-column>` components within `<e-columns>` for displaying data fields.
- Contains multiple `<modal-base>` components for confirmation, termination, and changing supervisor modals with respective templates.

#### mocks-talent-ng

- Contains a `<page-title>` component with `title="Employees"` attribute.
- Contains a `<grid-filters>` component with `centerTemplate` and `centerHeaderTemplate` attributes.
- The center header template includes a custom toolbar with:
  - `<input-text>` for search input.
  - `<button-dropdown-grid>` for toolbar buttons.
  - `<button-base>` for adding a new employee.
- The center content template includes an `<ejs-grid>` component with various attributes:
  - `[enableAdaptiveUI]="true"`
  - `[rowRenderingMode]="'Vertical'"`
  - `[allowPaging]="true"`
  - `[dataSource]="data"`
- Contains multiple `<e-column>` components within `<e-columns>` for displaying data fields.
- Contains multiple `<ng-template>` components for custom toolbar, right drawer content, and dropdown CTA.
- Contains multiple `<modal-base>` components for deleting and terminating employees with respective templates.

### Unique Markup Tags

#### AgileHR

- `talent-grid`
- `input-dropdown-multi`
- `input-datepicker`
- `input-multiline`

#### mocks-talent-ng

- `grid-filters`
- `centerTemplate`
- `centerHeaderTemplate`
- `input-text`
- `button-dropdown-grid`
- `button-base`

### Differences in Markup Structure

- **AgileHR** uses a `<talent-grid>` component with various attributes and event bindings, while **mocks-talent-ng** uses a `<grid-filters>` component with `centerTemplate` and `centerHeaderTemplate` attributes.
- **AgileHR** includes multiple `<input-dropdown-multi>` and `<input-dropdown>` components for filtering within a `<ng-template #filtersTemplate>`, while **mocks-talent-ng** includes a custom toolbar with `<input-text>`, `<button-dropdown-grid>`, and `<button-base>` components within a `<ng-template #centerHeaderTemplate>`.
- **mocks-talent-ng** includes additional attributes for adaptive UI and vertical row rendering in the `<ejs-grid>` component, which are not present in **AgileHR**.

### Summary

The primary differences between the two files are the layout structures and the components used for displaying grid filters and toolbars. **AgileHR** uses a `<talent-grid>` component with various attributes and event bindings, while **mocks-talent-ng** uses a `<grid-filters>` component with `centerTemplate` and `centerHeaderTemplate` attributes for custom grid filters. Additionally, **mocks-talent-ng** includes attributes for adaptive UI and vertical row rendering in the `<ejs-grid>` component.

### Prod Screenshots

![Alt Text](/path/to/img.jpg)

### Mock Screenshots

![Alt Text](/path/to/img.jpg)

### URL

[link to the page in pro](https://www.example.com)

[link to the page in mock](https://www.example.com)
