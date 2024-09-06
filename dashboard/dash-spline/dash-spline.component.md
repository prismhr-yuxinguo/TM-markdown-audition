<div class="dashboard__card">
    <dashboard-card-title [title]="'Appraisal Status Overview'">
        <input-dropdown [data]="monthsData"
                        [value]="value"
                        placeholder="Benefits Categories"
                        [floatLabelType]="'Never'"
                        (optionSelected)="onDropDownChange($event)"></input-dropdown>
    </dashboard-card-title>

    <dashboard-card-body>
        <br />
        <div class="preloader__wrapper" *ngIf="!showChart">
            <div class="preloader"></div>
        </div>

        <ejs-chart *ngIf="showChart"
                   [chartArea]="chartArea"
                   class="chart-wrapper"
                   id="aso-chart-container"
                   #splineChart
                   [enableCanvas]="false"
                   [primaryXAxis]="primaryXAxis"
                   [primaryYAxis]="primaryYAxis"
                   [title]="title"
                   [tooltip]="tooltip"
                   [annotations]="annotations"
                   [legendSettings]="legend"
                   [palettes]="palette">
            <e-series-collection>
                <e-series [dataSource]="sourceData"
                          type="Line"
                          xName="x"
                          yName="y"
                          width="2"
                          [marker]="marker"></e-series>
            </e-series-collection>
        </ejs-chart>

    </dashboard-card-body>
</div>

