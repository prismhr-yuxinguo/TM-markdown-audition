# Markup Audit Report

## Table of Contents

1. [File Paths](#file-paths)
2. [Unique Tags in Each File](#unique-tags-in-each-file)
3. [Differences in Markup Structure](#differences-in-markup-structure)
   - [Header Section](#header-section)
   - [Grid Component](#grid-component)
   - [Modals](#modals)
   - [Toolbar](#toolbar)
4. [Summary](#summary)

## File Paths

- `routing.component.html` belongs to the "AgileHR" project.
- `h-can-rout.component.html` belongs to the "Mocks-Talent-ng" project.

## Unique Tags in Each File

- **routing.component.html (AgileHR):**

  - `talent-grid`, `settings-table`, `settings-row`, `input-dropdown-multi`, `toggle-switch`, `input-multiline`, `modal-base`, `ng-template`

- **h-can-rout.component.html (Mocks-Talent-ng):**
  - `ejs-tab`, `e-tabitems`, `e-tabitem`, `grid-filters`, `input-text`, `button-new`, `ejs-grid`, `button-dropdown-grid`

## Differences in Markup Structure

### Header Section

- Both files use `<page-title [title]="'Route Candidate'"></page-title>` for the header.

### Grid Component

- **AgileHR:**

  - Uses `talent-grid` with various properties and columns defined using `e-columns` and `e-column`.
  - Includes custom templates for columns using `ng-template`.

- **Mocks-Talent-ng:**
  - Uses `ejs-grid` within a `grid-filters` component, with columns defined using `e-columns` and `e-column`.
  - Includes custom templates for columns using `ng-template`.

### Modals

- **AgileHR:**

  - Includes multiple `modal-base` components for different actions (e.g., route candidate, unroute candidate, send reminder).
  - Uses `ng-template` elements for modal content.

- **Mocks-Talent-ng:**
  - Does not include any modal components.

### Toolbar

- **AgileHR:**

  - Does not include a custom toolbar.

- **Mocks-Talent-ng:**
  - Includes a custom toolbar within `grid-filters`, using `input-text` for search and `button-new` for adding a new route.

## Summary

The primary differences between the two files are in the use of grid components, modals, and toolbars. The `routing.component.html` file from "AgileHR" uses `talent-grid` for the grid and includes multiple `modal-base` components for different actions. It also includes `ng-template` elements for custom column templates and modal content. The `h-can-rout.component.html` file from "Mocks-Talent-ng" uses `ejs-grid` within a `grid-filters` component and includes a custom toolbar. It does not include any modal components.

## Prod Screenshots

![Alt Text](./img-dev.jpg)

## Mocks Screenshots

![Alt Text](./img-mocks.jpg)

## Prod URL

[link to the page in prod](https://piedpiper.agilehr.net/hiring/candidates/candidate_01j2h56ecpe0wbkf1d21z8w2fj/routing)

## Mocks URL

[link to the page in mock](http://localhost:4340/candidates/:id/h-can-deet)
