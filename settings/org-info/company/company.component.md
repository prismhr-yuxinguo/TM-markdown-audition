# Differences between `company.component.html` and `s-o-info.component.html`

## Table of Contents

-   [Relative Paths](#relative-paths)
-   [Differences](#differences)
-   [Prod Screenshots](#prod-screenshots)
-   [Mock Screenshots](#mock-screenshots)
-   [URL](#url)

### Relative Paths

-   **company.component.html**: `AgileHR\Talent\Talent.Web\ClientApp\src\app\settings\org-info\company\company.component.html`
-   **s-o-info.component.html**: `components-ng-shared\projects\mocks-talent-ng\src\app\settings\org-info\s-o-info\s-o-info.component.html`

### Differences

#### AgileHR\Talent\Talent.Web\ClientApp\src\app\settings\org-info\company\company.component.html

-   Contains a `<page-title>` component with a `[title]` attribute set to `'Company Information'`.
-   Contains a `<talent-footer>` component with attributes `[nextVisible]`, `[prevVisible]`, `(saveClicked)`, `[saveEnabled]`, and `[saveVisible]`.
-   Contains a `<fieldset>` element with a `[formGroup]` attribute bound to `orgInfoForm` and `[disabled]` bound to `!hasEdit`.
-   The `<fieldset>` contains a `<settings-table>` component with multiple `<settings-row>` components.
-   The `<settings-row>` components have attributes `[title]`, `[description]`, and `[required]`.
-   The `<settings-row>` components contain various input components such as `<input-text>`, `<input-dropdown>`, and `<ejs-maskedtextbox>`.
-   The `<input-text>` components have attributes `[placeholder]`, `[required]`, `[form]`, and `formControlName`.
-   The `<input-dropdown>` component has attributes `[data]`, `[form]`, `formControlName`, `[placeholder]`, `[enableFiltering]`, `[filtering]`, and `[required]`.
-   The `<ejs-maskedtextbox>` component has attributes `form`, `formControlName`, `mask`, `placeholder`, `floatLabelType`, and `required`.
-   Contains a `<p>` element with an `*ngIf` directive bound to `orgInfoForm.controls.maskedZipCode.invalid && orgInfoForm.controls.maskedZipCode.touched` and class `error-message masked-value-error-message`.

#### components-ng-shared\projects\mocks-talent-ng\src\app\settings\org-info\s-o-info\s-o-info.component.html

-   Contains a `<settings-table>` component with multiple `<settings-row>` components.
-   The `<settings-row>` components have attributes `[title]` and `[required]`.
-   The `<settings-row>` components contain various input components such as `<input-text>` and `<input-dropdown>`.
-   The `<input-text>` components have attributes `[placeholder]` and `[required]`.
-   The `<input-dropdown>` component has attributes `[data]`, `[placeholder]`, `[enableFiltering]`, `[filtering]`, and `[required]`.

### Prod Screenshots

![Prod Screenshot](./company-prod.png)

### Mock Screenshots

![Mock Screenshot](./s-o-info-mock.png)

### URL

[link to the page in prod](https://piedpiper.agilehr.net/core/settings/org-info/company)

[link to the page in mock environment](http://localhost:4340/settings/organization-information)
