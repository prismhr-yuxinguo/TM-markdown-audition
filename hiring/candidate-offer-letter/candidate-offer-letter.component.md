# Markup Audit Report

## Table of Contents

1. [File Paths](#file-paths)
2. [Unique Tags in Each File](#unique-tags-in-each-file)
3. [Differences in Markup Structure](#differences-in-markup-structure)
   - [Header Section](#header-section)
   - [Status Section](#status-section)
   - [Offer Letter Content](#offer-letter-content)
   - [Next Step Section](#next-step-section)
   - [Modals](#modals)
4. [Summary](#summary)

## File Paths

- `candidate-offer-letter.component.html` belongs to the "AgileHR" project.
- The file from "Mocks-Talent-ng" is not available.

## Unique Tags in Each File

- **candidate-offer-letter.component.html (AgileHR):**
  - `page-title`, `div`, `img`, `b`, `span`, `i`, `button`, `input-multiline`, `input-text`, `input-ssn`, `input-datepicker`, `modal-base`, `ng-template`

## Differences in Markup Structure

### Header Section

- **AgileHR:**
  - Uses `<page-title [title]="'Offer Letter'"></page-title>` for the header.
  - Includes a header section with client name and instructions.

### Status Section

- **AgileHR:**
  - Displays status information using `div` elements with `alert` classes.
  - Includes status for accepted and declined offers with corresponding icons and notes.

### Offer Letter Content

- **AgileHR:**
  - Uses a `div` with `card` and `card-body` classes to display the offer letter content.
  - Includes conditional rendering for loading state and offer letter content.
  - Displays signature information with date and time.

### Next Step Section

- **AgileHR:**
  - Uses a `div` with `card` and `card-title` classes to display the next step section.
  - Includes buttons for accepting and declining the offer with corresponding modals.

### Modals

- **AgileHR:**
  - Includes two modals: one for accepting the offer and one for declining the offer.
  - Uses `modal-base` and `ng-template` for modal content.
  - Includes form elements within the modals for capturing user input.

## Summary

The primary differences in the markup structure of the `candidate-offer-letter.component.html` file from "AgileHR" include the use of a header section with `page-title`, status sections with `alert` classes, offer letter content within a `card`, a next step section with buttons for accepting and declining the offer, and modals for capturing user input. The file from "Mocks-Talent-ng" is not available for comparison.

## Prod Screenshots

Not Found

## Mocks Screenshots

Not Found

## Prod URL

Not Found

## Mocks URL

Not Found
