# Differences between `dash-gage1.component.html` (Mocks) and `dash-gage1.component.html` (Production)

## Table of Contents

-   [Relative Paths](#relative-paths)
-   [Differences](#differences)
-   [Prod Screenshots](#prod-screenshots)
-   [Mock Screenshots](#mock-screenshots)
-   [URL](#url)

### Relative Paths

-   **dash-gage1.component.html (Mocks)**: `components-ng-shared/projects/mocks-talent-ng/src/app/dashboard/dash-gage1/dash-gage1.component.html`
-   **dash-gage1.component.md (Production)**: `AgileHR/Talent/Talent.Web/ClientApp/src/app/dashboard/dash-gage1/dash-gage1.component.md`

### Differences

#### components-ng-shared/projects/mocks-talent-ng/src/app/dashboard/dash-gage1/dash-gage1.component.html

-   Contains an `<ejs-circulargauge>` component with attributes `[width]`, `[height]`, `title`, `[titleStyle]`, and `background`.
-   The `<e-axis>` component has attributes `startAngle`, `endAngle`, `minimum`, `maximum`, `[majorTicks]`, `[minorTicks]`, `[lineStyle]`, `[labelStyle]`, `[annotations]`, and `[ranges]`.
-   The `<e-pointers>` component is empty.

#### AgileHR/Talent/Talent.Web/ClientApp/src/app/dashboard/dash-gage1/dash-gage1.component.html

-   Contains an `<ejs-circulargauge>` component with attributes `style`, `[width]`, `[height]`, `title`, `[titleStyle]`, and `background`.
-   The `<e-axis>` component has attributes `startAngle`, `endAngle`, `minimum`, `maximum`, `[majorTicks]`, `[minorTicks]`, `[lineStyle]`, `[labelStyle]`, `[annotations]`, and `[ranges]`.
-   The `<e-pointers>` component is empty.

### This component is currently not implemented in production.

### Production Screenshots

N/A

### Mock Screenshots

N/A

### URL

N/A
