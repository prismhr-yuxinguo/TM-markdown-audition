# Markup Audit Report

## Table of Contents

1. [File Paths](#file-paths)
2. [Differences in Markup Structure](#differences-in-markup-structure)
   - [Unique Tags in Each File](#unique-tags-in-each-file)
   - [Header Section](#header-section)
   - [Grid Component](#grid-component)
   - [Toolbar](#toolbar)
   - [Modals](#modals)
   - [Right Drawer](#right-drawer)
   - [Form Elements](#form-elements)
3. [Summary](#summary)

## File Paths

- `activity.component.html` belongs to the "AgileHR" project.
- `h-activity.component.html` belongs to the "Mocks-Talent-ng" project.

## Differences in Markup Structure

### Unique Tags in Each File

- **activity.component.html (AgileHR):**

  - `talent-grid`, `modal-base`, `ng-template`, `settings-table`, `settings-row`, `input-multiline`

- **h-activity.component.html (Mocks-Talent-ng):**
  - `layout-drawers`, `layout-drawer-center`, `grid-filters`, `input-text`, `button-dropdown-grid`, `ejs-grid`, `layout-drawer-right`, `layout-toolbox`, `app-hr-drawer`

### Header Section

- Both files include a `page-title` component with the title "Activity".

### Grid Component

- `activity.component.html` uses `talent-grid` with various properties and columns defined using `e-columns` and `e-column`.
- `h-activity.component.html` uses `ejs-grid` within a `grid-filters` component, with columns defined using `e-columns` and `e-column`.

### Toolbar

- `h-activity.component.html` includes a custom toolbar within a `grid-filters` component, using `input-text` for search and `button-dropdown-grid` for options.
- `activity.component.html` does not include a custom toolbar.

### Modals

- `activity.component.html` includes two `modal-base` components for delete and edit actions, with corresponding `ng-template` elements for the modal content.
- `h-activity.component.html` does not include any modal components.

### Right Drawer

- `h-activity.component.html` includes a right drawer using `layout-drawer-right` and `layout-toolbox`, containing an `app-hr-drawer` component.
- `activity.component.html` does not include a right drawer. The drawer is in `app-requisitions-detail`.

### Form Elements

- `activity.component.html` includes form elements within the edit modal, such as `settings-table`, `settings-row`, and `input-multiline`.
- `h-activity.component.html` does not include any form elements.

## Summary

The primary differences between the two files are in the structure and components used for the grid, toolbar, modals, and right drawer. The `activity.component.html` file from "AgileHR" uses `talent-grid` for the grid and includes modals for delete and edit actions, with form elements within the edit modal. The `h-activity.component.html` file from "Mocks-Talent-ng" uses `ejs-grid` within a `grid-filters` component and includes a custom toolbar and a right drawer with an `app-hr-drawer` component.

## Prod Screenshots

![Alt Text](./img-dev.jpg)

## Mocks Screenshots

![Alt Text](./img-mocks.jpg)

## Prod URL

[link to the page in prod](https://piedpiper.agilehr.net/hiring/requisitions/requisition_1wzdr73jygxr8stqr01mx6tna3/activity)

## Mocks URL

[link to the page in mock](http://localhost:4340/hiring/requisitions/:id/h-activity)
