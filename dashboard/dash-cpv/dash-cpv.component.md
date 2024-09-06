<div class="dashboard__card">
    <dashboard-card-title [title]="'Career Portal Views'">
        <ejs-dropdownlist id="ddlelement"
                          [dataSource]="monthsData"
                          [value]="'Last12Months'"
                          [fields]="fields"
                          (change)="onDropDownChange($event)"></ejs-dropdownlist>
    </dashboard-card-title>
    <dashboard-card-body>
        <br />
        <div class="preloader__wrapper" *ngIf="!showChart">
            <div class="preloader"></div>
        </div>
        <ejs-chart *ngIf="showChart"
                   [chartArea]="chartArea"
                   class="chart-wrapper"
                   #cpvChart
                   id="cpv-chart-container"
                   [enableCanvas]="false"
                   [primaryXAxis]="primaryXAxis"
                   [primaryYAxis]="primaryYAxis"
                   [title]="title"
                   [tooltip]="tooltip"
                   [legendSettings]="legend"
                   [palettes]="palette">
          <e-series-collection>
            <e-series [dataSource]="sourceData"
                      type="Spline"
                      xName="x"
                      yName="y"
                      name="Page Views"
                      width="2"
                      [marker]="marker"></e-series>
          </e-series-collection>
        </ejs-chart>
    </dashboard-card-body>
</div>
