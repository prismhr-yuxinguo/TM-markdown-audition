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

- **AgileHR**: `AgileHR/Talent/Talent.Web/ClientApp/src/app/employees/employee-sidebar/employee-sidebar.component.html`
- **mocks-talent-ng**: `components-ng-shared/projects/mocks-talent-ng/src/app/employees/employee-sidebar/employee-sidebar.component.html`

### Differences in Markup Structure

#### AgileHR

- Contains a `<div class="sidebar__wrapper">` section.
- Includes an `<input-dropdown>` component with attributes:
  - `[data]=""`
  - `[placeholder]="'Employee Name'"`
- Contains a `<div class="sidebar__employee">` section with nested `<div class="sidebar__employee__image">` and `<div class="sidebar__employee__data">` sections.
- The employee image section includes:
  - An `<img>` element with attributes:
    - `src="./../../../assets/img/placeholders/ceo.jpg"`
    - `alt="Portrait of Johm Doe, CEO"`
    - `role="img"`
- The employee data section includes multiple `<span>` elements for displaying employee details.
- Contains multiple `<div class="drawers__value">` sections with nested `<span>` elements for displaying department, division, office location, and supervisor email.

#### mocks-talent-ng

- Contains a `<div class="sidebar__wrapper">` section.
- Includes an `<input-dropdown>` component with attributes:
  - `[data]="data"`
  - `[placeholder]="'Employee Name'"`
- Contains a `<div class="sidebar__employee">` section with nested `<div class="sidebar__employee__image">` and `<div class="sidebar__employee__data">` sections.
- The employee image section includes:
  - An `<img>` element with attributes:
    - `src="./../../../assets/img/placeholders/ceo.jpg"`
    - `alt="Portrait of Johm Doe, CEO"`
- The employee data section includes multiple `<span>` elements for displaying employee details.
- Contains multiple `<div class="drawers__value">` sections with nested `<span>` elements for displaying department, division, office location, and supervisor email.

### Unique Markup Tags

#### AgileHR

- `input-dropdown` (with `[data]=""`)
- `img` (with `role="img"`)

#### mocks-talent-ng

- `input-dropdown` (with `[data]="data"`)

### Differences in Markup Structure

- **AgileHR** uses an `<input-dropdown>` component with `[data]=""`, while **mocks-talent-ng** uses `[data]="data"`.
- The `<img>` element in **AgileHR** includes a `role="img"` attribute, which is not present in **mocks-talent-ng**.

### Summary

The primary differences between the two files are the attributes used in the `<input-dropdown>` and `<img>` elements. **AgileHR** uses `[data]=""` for the `<input-dropdown>` component and includes a `role="img"` attribute in the `<img>` element, while **mocks-talent-ng** uses `[data]="data"` for the `<input-dropdown>` component and does not include the `role="img"` attribute in the `<img>` element.

### Prod Screenshots

![Alt Text](/path/to/img.jpg)

### Mock Screenshots

![Alt Text](/path/to/img.jpg)

### URL

[link to the page in pro](https://www.example.com)

[link to the page in mock](https://www.example.com)
