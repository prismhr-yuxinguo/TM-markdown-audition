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

- **AgileHR**: `AgileHR/Talent/Talent.Web/ClientApp/src/app/employees/employee-additional/personal-information/personal-information.component.html`
- **mocks-talent-ng**: `components-ng-shared/projects/mocks-talent-ng/src/app/employees/employee-additional/personal-information/personal-information.component.html`

### Differences in Markup Structure

#### AgileHR

- Contains a `<fieldset>` element with `[formGroup]` and `[disabled]` attributes.
- Contains a `<div>` element with a nested `<div formGroupName="personalInformation">`.
- Contains a `<settings-table>` component.
- Uses conditional rendering with `@if(isHcmSynced)` to disable certain fields.
- Contains multiple `<settings-row>` components with `[title]`, `[required]`, and `[description]` attributes.
- Each `<settings-row>` contains different input components:
  - `<input-text>` for first name, preferred name, middle name, last name, username, email, address, address 2, city, and zip code inputs.
  - `<input-dropdown>` for state and country inputs.
  - `<ejs-maskedtextbox>` for masked zip code input.
- Uses different forms (`personalInfoDisabledForm` and `employeeForm.get('personalInformation')`) based on the `isHcmSynced` condition.

#### mocks-talent-ng

- Contains a `<settings-table>` component.
- Contains multiple `<settings-row>` components with `[title]`, `[description]`, and `[required]` attributes.
- Each `<settings-row>` contains different input components:
  - `<input-text>` for first name, preferred name, middle name, last name, email, address, address 2, city, and zip code inputs.
  - `<input-dropdown>` for state and country inputs.

### Unique Markup Tags

#### AgileHR

- `fieldset`
- `div` (with `formGroupName="personalInformation"`)
- `input-text` (with `[form]="personalInfoDisabledForm"` or `[form]="employeeForm.get('personalInformation')"` based on `isHcmSynced`)
- `ejs-maskedtextbox`

#### mocks-talent-ng

- None

### Differences in Markup Structure

- **AgileHR** uses a `<fieldset>` element with conditional rendering based on `isHcmSynced`, while **mocks-talent-ng** does not.
- **AgileHR** uses different forms (`personalInfoDisabledForm` and `employeeForm.get('personalInformation')`) based on the `isHcmSynced` condition, while **mocks-talent-ng** uses a single form for all input components.
- **AgileHR** includes an `<ejs-maskedtextbox>` component for masked zip code input, which is not present in **mocks-talent-ng**.

### Summary

The primary differences between the two files are the use of a `<fieldset>` element with conditional rendering based on `isHcmSynced` in **AgileHR**, and the use of different forms based on the `isHcmSynced` condition. **mocks-talent-ng** uses a simpler structure with a single form for all input components. Additionally, **AgileHR** includes an `<ejs-maskedtextbox>` component for masked zip code input, which is not present in **mocks-talent-ng**.

### Prod Screenshots

![Alt Text](/path/to/img.jpg)

### Mock Screenshots

![Alt Text](/path/to/img.jpg)

### URL

[link to the page in pro](https://www.example.com)

[link to the page in mock](https://www.example.com)
