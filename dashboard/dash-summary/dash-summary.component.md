<div class="dashboard__card">
    <dashboard-card-title [title]="'Candidate Summary'"> </dashboard-card-title><dashboard-card-body>
        <ejs-chart id="chart-container"
                   [primaryXAxis]="primaryXAxis"
                   [primaryYAxis]="primaryYAxis"
                   [title]="title"
                   #summarChart
                   [palettes]="palette">
            <e-series-collection>
                <e-series [dataSource]="chartData"
                          type="Column"
                          xName="Title"
                          yName="YC"
                          name="Yearly Candidates"
                          width="2"
                          [marker]="marker"
                          columnSpacing="0.1"
                          tooltipMappingName="MappingName">
                </e-series>
                <e-series [dataSource]="chartData"
                          type="Column"
                          xName="Title"
                          yName="MC"
                          name="Monthly Candidates"
                          width="2"
                          [marker]="marker"
                          columnSpacing="0.1"
                          tooltipMappingName="MappingName">
                </e-series>
                <e-series [dataSource]="chartData"
                          type="Column"
                          xName="Title"
                          yName="TC"
                          name="Today's Candidates"
                          width="2"
                          [marker]="marker"
                          columnSpacing="0.1"
                          tooltipMappingName="MappingName">
                </e-series>
                <e-series [dataSource]="chartData"
                          type="Column"
                          xName="Title"
                          yName="AR"
                          name="Active Requisitions"
                          width="2"
                          [marker]="marker"
                          columnSpacing="0.1"
                          tooltipMappingName="MappingName">
                </e-series>
                <e-series [dataSource]="chartData"
                          type="Column"
                          xName="Title"
                          yName="PR"
                          name="Published Requisitions"
                          width="2"
                          [marker]="marker"
                          columnSpacing="0.1"
                          tooltipMappingName="MappingName">
                </e-series>
                <e-series [dataSource]="chartData"
                          type="Column"
                          xName="Title"
                          yName="IP"
                          name="In Progress Requisitions"
                          width="2"
                          [marker]="marker"
                          columnSpacing="0.1"
                          tooltipMappingName="MappingName">
                </e-series>
                <e-series [dataSource]="chartData"
                          type="Column"
                          xName="Title"
                          yName="FY"
                          name="Filled Requisitions (Year)"
                          width="2"
                          [marker]="marker"
                          columnSpacing="0.1"
                          tooltipMappingName="MappingName">
                </e-series>
                <e-series [dataSource]="chartData"
                          type="Column"
                          xName="Title"
                          yName="ATC"
                          name="All-Time Candidates"
                          width="2"
                          [marker]="marker"
                          columnSpacing="0.1"
                          tooltipMappingName="MappingName">
                </e-series>
            </e-series-collection>
        </ejs-chart>
    </dashboard-card-body>
</div>