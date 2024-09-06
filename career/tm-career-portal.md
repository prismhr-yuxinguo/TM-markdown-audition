# Differences between `tm-career-portal.component.html` and `new-bonus.component.html`

## Table of Contents

- [Relative Paths](#relative-paths)
- [Differences](#differences)
- [Prod Screenshots](#prod-screenshots)
- [Mock Screenshots](#mock-screenshots)
- [URL](#url)

### Relative Paths

- **tm-career-portal.component.html**: `AgileHR/Talent/Talent.Web/ClientApp/src/app/careers/career-portal-landing/tm-career-portal/tm-career-portal.component.html`
- **new-bonus.component.html**: `AgileHR/Talent/Talent.Web/ClientApp/src/app/employees/employee-additional/compensation/manage-bonus/new-bonus/new-bonus.component.html`

### Differences

#### AgileHR/Talent/Talent.Web/ClientApp/src/app/careers/career-portal-landing/tm-career-portal/tm-career-portal.component.html

- Contains a `<div>` with class `careers__header-logo` and an `<img>` tag for displaying a logo.
- Contains a `<nav>` element with a list of navigation links.
- Contains a `<section>` with class `careers__right-col`.
- Contains a `<div>` with class `careers__toolbar` that includes:
  - A `<div>` with class `careers__toolbar-top` containing:
    - An `<a>` tag for viewing all jobs.
    - An `<a>` tag for viewing the website.
    - A `<button-base>` component for closing filters.
  - A `<div>` with class `careers__toolbar-form` containing:
    - An `<input-text>` component for search.
    - Two `<input-dropdown-multi>` components for department and location filters.
- Contains a `<div>` with class `careers__welcome` that includes:
  - A `<div>` with class `careers__welcome-header` containing:
    - An `<h2>` tag with a welcome message.
    - A `<button-base>` component for opening full screen.
  - Multiple `<h3>` and `<p>` tags with various content about the company, hiring philosophy, FAQs, and office locations.

#### AgileHR/Talent/Talent.Web/ClientApp/src/app/employees/employee-additional/compensation/manage-bonus/new-bonus/new-bonus.component.html

- Contains a `<settings-table>` component with a `[settingsTitle]` attribute and `[formGroup]` attribute.
- Contains multiple `<settings-row>` components with `[title]`, `[description]`, and `[required]` attributes.
- Each `<settings-row>` contains different input components:
  - `<input-datepicker>` for date input.
  - `<input-numeric>` for amount input.
  - `<input-dropdown>` for reason input.
  - `<input-multiline>` for comment input.

### Prod Screenshots

![Alt Text](/assets/img/tm-career-portal-prod.jpg)

### Mock Screenshots

![Alt Text](/assets/img/tm-career-portal-mock.jpeg)

### URL

[link to the page in pro](https://piedpiper.agilehr.net/core/employees)
