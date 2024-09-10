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

- **AgileHR**: `AgileHR/Talent/Talent.Web/ClientApp/src/app/employees/employee-additional/forms/forms.component.html`
- **mocks-talent-ng**: `components-ng-shared/projects/mocks-talent-ng/src/app/employees/employee-additional/forms/forms.component.html`

### Differences in Markup Structure

#### AgileHR

- Contains a `<page-title>` component with `[title]="'Document Management'"` attribute.
- Contains a `<div class="grid-filters">` section with nested `<div class="grid-filters__left">`, `<div class="grid-filters__center">`, and `<div class="grid-filters__right">` sections.
- The left section includes:
  - A title with a `<button-base>` component for closing filters.
  - A wrapper `<div class="grid-filters__left-wrapper">`.
- The center section includes:
  - An `<ejs-grid>` component with attributes for paging and data source.
  - A custom toolbar template with:
    - A search bar.
    - A button for toggling search filters.
    - A dropdown grid button for toolbar options.
    - A button for adding a new document.
  - An advanced search list with multiple items.
- The right section is empty.
- Contains multiple `<ng-template>` components for custom toolbar, description text, and edit button.
- The description text template includes an `<ejs-tooltip>` component for displaying tooltips.

#### mocks-talent-ng

- Contains a `<page-title>` component with `[title]="'Document Management'"` attribute.
- Contains a `<grid-filters>` component with `centerTemplate` and `centerHeaderTemplate` attributes.
- The center header template includes a custom toolbar with:
  - A search bar.
  - A dropdown grid button for toolbar options.
  - A button for adding a new document.
- The center content template includes:
  - An `<ejs-grid>` component with attributes for adaptive UI, vertical row rendering, paging, and data source.
  - Multiple columns for displaying data fields.
- Contains multiple `<ng-template>` components for custom toolbar, description text, and edit button.
- The description text template includes a `<popover>` component for displaying popovers.

### Unique Markup Tags

#### AgileHR

- `div` (with class `grid-filters`, `grid-filters__left`, `grid-filters__center`, `grid-filters__right`, `grid-filters__left-title`, `grid-filters__left-wrapper`)
- `button-base` (for closing filters, toggling search filters, and adding a new document)
- `ejs-tooltip`

#### mocks-talent-ng

- `grid-filters`
- `centerTemplate`
- `centerHeaderTemplate`
- `popover`

### Differences in Markup Structure

- **AgileHR** uses a `<div>` based structure for the grid filters, while **mocks-talent-ng** uses a `<grid-filters>` component with `centerTemplate` and `centerHeaderTemplate` attributes.
- **AgileHR** includes an advanced search list with multiple items, while **mocks-talent-ng** does not.
- **AgileHR** uses an `<ejs-tooltip>` component for displaying tooltips in the description text template, while **mocks-talent-ng** uses a `<popover>` component for displaying popovers.

### Summary

The primary differences between the two files are the layout structures and the components used for displaying grid filters and toolbars. **AgileHR** uses a `<div>` based structure with an advanced search list and tooltips for description text, while **mocks-talent-ng** uses a `<grid-filters>` component with a simpler structure and popovers for description text.

### Prod Screenshots

![Alt Text](/path/to/img.jpg)

### Mock Screenshots

![Alt Text](/path/to/img.jpg)

### URL

[link to the page in prod](https://www.example.com)

[link to the page in mock](https://www.example.com)
