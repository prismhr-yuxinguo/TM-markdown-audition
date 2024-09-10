# Markup Audit Report

## Table of Contents

1. [File Paths](#file-paths)
2. [Unique Tags in Each File](#unique-tags-in-each-file)
3. [Differences in Markup Structure](#differences-in-markup-structure)
   - [Header Section](#header-section)
   - [Grid Component](#grid-component)
   - [Filters](#filters)
   - [Modals](#modals)
4. [Summary](#summary)

## File Paths

- `activity.component.html` belongs to the "AgileHR" project.
- `h-can-activity.component.html` belongs to the "Mocks-Talent-ng" project.

## Unique Tags in Each File

- **activity.component.html (AgileHR):**

  - `page-title`, `talent-grid`, `input-dropdown-multi`, `e-columns`, `e-column`, `button-dropdown-grid`, `modal-base`, `settings-table`, `settings-row`, `input-text`, `toggle-switch`

- **h-can-activity.component.html (Mocks-Talent-ng):**
  - `grid-filters`, `input-text`, `button-dropdown-grid`, `ejs-grid`, `popover`

## Differences in Markup Structure

### Header Section

- **AgileHR:**

  - Uses `<page-title [title]="'Activity'"></page-title>` for the header.

- **Mocks-Talent-ng:**
  - Does not include a header section.

### Grid Component

- **AgileHR:**

  - Uses `talent-grid` with various properties and columns defined using `e-columns` and `e-column`.
  - Includes custom templates for columns using `ng-template`.

- **Mocks-Talent-ng:**
  - Uses `ejs-grid` within a `grid-filters` component, with columns defined using `e-columns` and `e-column`.
  - Includes custom templates for columns using `ng-template`.

### Filters

- **AgileHR:**

  - Includes `input-dropdown-multi` components for filtering activity types and requisitions.
  - Uses `ng-template` for filter templates.

- **Mocks-Talent-ng:**
  - Uses `grid-filters` with `centerTemplate` and `centerHeaderTemplate` for filtering.
  - Includes `input-text` for search and `button-dropdown-grid` for filter options.

### Modals

- **AgileHR:**

  - Includes multiple `modal-base` components for different actions (e.g., create/edit note, delete note).
  - Uses `ng-template` elements for modal content.
  - Includes `settings-table` and `settings-row` components for form layout within modals.

- **Mocks-Talent-ng:**
  - Does not include any modal components.

## Summary

The primary differences between the two files are in the use of header sections, grid components, filters, and modals. The `activity.component.html` file from "AgileHR" includes a header section with `page-title`, uses `talent-grid` for the grid, and includes multiple `modal-base` components for different actions. It also includes `input-dropdown-multi` components for filtering and `settings-table` and `settings-row` components for form layout within modals. The `h-can-activity.component.html` file from "Mocks-Talent-ng" uses `ejs-grid` within a `grid-filters` component and includes `input-text` for search and `button-dropdown-grid` for filter options. It does not include any modal components.

## Prod Screenshots

![Alt Text](./img-dev.jpg)

## Mocks Screenshots

![Alt Text](./img-mocks.jpg)

## Prod URL

[link to the page in prod](https://piedpiper.agilehr.net/hiring/candidates/candidate_01j2h56ecpe0wbkf1d21z8w2fj/activity)

## Mocks URL

[link to the page in mock](http://localhost:4340/candidates/:id/h-can-deet)
