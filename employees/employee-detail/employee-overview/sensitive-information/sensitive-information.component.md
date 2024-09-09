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

- **AgileHR**: `AgileHR/Talent/Talent.Web/ClientApp/src/app/employees/employee-additional/sensitive-information/sensitive-information.component.html`
- **mocks-talent-ng**: `components-ng-shared/projects/mocks-talent-ng/src/app/employees/employee-additional/sensitive-information/sensitive-information.component.html`

### Differences in Markup Structure

#### AgileHR

- Contains a `<fieldset>` element with `[disabled]="disabled"` attribute.
- Contains a `<settings-table>` component.
- Contains multiple `<settings-row>` components with `[title]`, `[description]`, and `[required]` attributes.
- Each `<settings-row>` contains different input components:
  - `<input-dropdown>` for gender, race, veteran’s status, and disability inputs.
- Uses `[form]="employeeForm.get('sensitiveInformation')"` and `formControlName` attributes for form control.

#### mocks-talent-ng

- Contains a `<settings-table>` component.
- Contains multiple `<settings-row>` components with `[title]`, `[description]`, and `[required]` attributes.
- Each `<settings-row>` contains different input components:
  - `<input-phone>` for SSN input.
  - `<input-datepicker>` for date of birth input.
  - `<input-dropdown>` for gender, race, ethnicity, veteran’s status, and disability inputs.

### Unique Markup Tags

#### AgileHR

- `fieldset`
- `input-dropdown` (with `[form]="employeeForm.get('sensitiveInformation')"` and `formControlName` attributes)

#### mocks-talent-ng

- `input-phone`
- `input-datepicker`

### Differences in Markup Structure

- **AgileHR** uses a `<fieldset>` element with a `[disabled]="disabled"` attribute, while **mocks-talent-ng** does not.
- **AgileHR** uses `[form]="employeeForm.get('sensitiveInformation')"` and `formControlName` attributes for form control, while **mocks-talent-ng** does not.
- **mocks-talent-ng** includes additional input components such as `<input-phone>` for SSN and `<input-datepicker>` for date of birth, which are not present in **AgileHR**.

### Summary

The primary differences between the two files are the use of a `<fieldset>` element with a `[disabled]="disabled"` attribute and form control attributes in **AgileHR**, and the inclusion of additional input components such as `<input-phone>` for SSN and `<input-datepicker>` for date of birth in **mocks-talent-ng**.

### Prod Screenshots

![Alt Text](/path/to/img.jpg)

### Mock Screenshots

![Alt Text](/path/to/img.jpg)

### URL

[link to the page in pro](https://www.example.com)

[link to the page in mock](https://www.example.com)
