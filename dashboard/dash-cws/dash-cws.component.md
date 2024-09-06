<div class="dashboard__card">
  <dashboard-card-title [title]="'Candidate Workflow Status'">
    <input-dropdown 
    [ngClass]="{
      'custom-notallowed-cursor': showChart
    }"
     [form]="filtersForm" formControlName="requisitions" [data]="requisitionsData"
      [placeholder]="'Choose Requisition'" [floatLabelType]="'Never'"
      (optionSelected)="onDropDownChange($event)"></input-dropdown>
  </dashboard-card-title>
  <dashboard-card-body>
    <div class="preloader__wrapper" *ngIf="showChart">
      <div class="preloader"></div>
    </div>
    <div *ngIf="!showChart && !chartData?.length">
      No data available to display.
    </div>
    <div class="chart-container">
    <ejs-accumulationchart class="custom-cursor" *ngIf="!showChart && chartData?.length" #cwsChart [legendSettings]="legendSettings"
      [tooltip]="tooltip" [title]="title" [enableSmartLabels]="enableSmartLabels" [enableAnimation]="enableAnimation"
      [enableBorderOnMouseMove]="false" (pointClick)="onSectionClick($event)">
      <e-accumulation-series-collection>
        <e-accumulation-series [dataSource]="chartData" xName="Status" yName="Count" innerRadius="40%"
          [dataLabel]="dataLabel" [radius]="radius" tooltipMappingName="Radius" [palettes]="palette">
        </e-accumulation-series>
      </e-accumulation-series-collection>
    </ejs-accumulationchart>
   </div>
   
  </dashboard-card-body>
</div>