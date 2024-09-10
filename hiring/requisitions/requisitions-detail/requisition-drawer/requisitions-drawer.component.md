# Markup Audit Report

## Table of Contents

1. [File Paths](#file-paths)
2. [Unique Tags in Each File](#unique-tags-in-each-file)
3. [Differences in Markup Structure](#differences-in-markup-structure)
   - [Form Group](#form-group)
   - [Input Dropdown](#input-dropdown)
   - [Data Binding](#data-binding)
4. [Summary](#summary)

## File Paths

- `requisitions-drawer.component.html` belongs to the "AgileHR" project.
- `hr-drawer.component.html` belongs to the "Mocks-Talent-ng" project.

## Differences in Markup Structure

### Unique Tags in Each File

- **requisitions-drawer.component.html (AgileHR):**

  - `form`, `formGroup`, `formControlName`, `callback`, `enableFiltering`, `filtering`

- **hr-drawer.component.html (Mocks-Talent-ng):**
  - None

### Differences in Markup Structure

1. **Form Group:**

   - `requisitions-drawer.component.html` includes a `formGroup` directive on the `div` element and uses `formControlName` on the `input-dropdown` component.
   - `hr-drawer.component.html` does not include a `formGroup` directive or `formControlName`.

2. **Input Dropdown:**

   - `requisitions-drawer.component.html` includes additional attributes on the `input-dropdown` component such as `enableFiltering`, `filtering`, `callback`, and `form`.
   - `hr-drawer.component.html` only includes `data` and `placeholder` attributes on the `input-dropdown` component.

3. **Data Binding:**
   - `requisitions-drawer.component.html` uses Angular interpolation to bind values dynamically (e.g., `{{ id }}`, `{{ daysOpen }}`, `{{ status }}`).
   - `hr-drawer.component.html` uses static values for the same fields (e.g., `184`, `24`, `In Progress`).

## Summary

The primary differences between the two files are in the use of form directives, additional attributes on the `input-dropdown` component, and data binding methods. The `requisitions-drawer.component.html` file from "AgileHR" includes a `formGroup` directive and uses dynamic data binding with Angular interpolation, while the `hr-drawer.component.html` file from "Mocks-Talent-ng" uses static values and does not include form directives or additional attributes on the `input-dropdown` component.

## Prod Screenshots

![Alt Text](./img-dev.jpg)

## Mocks Screenshots

![Alt Text](./img-mocks.jpg)

## Prod URL

[link to the page in prod](https://piedpiper.agilehr.net/hiring/requisitions/requisition_01j203caetfqpangs4gptyke4k/requisition-info/position-details)

## Mocks URL

[link to the page in mock](http://localhost:4340/hiring/requisitions/1/req-workflow/position-details)
