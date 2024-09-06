<div class="dashboard__card">
    <dashboard-card-title [title]="'Current Hiring Pipeline'"></dashboard-card-title><dashboard-card-body>
        <ejs-accumulationchart id="container"
                               #pie
                               width="300px"
                               height="300px"
                               [centerLabel]="centerLabel"
                               (pointRender)="pointRender($event)"
                               [legendSettings]="legendSettings"
                               [enableBorderOnMouseMove]="false">
            <e-accumulation-series-collection>
                <e-accumulation-series name="Project"
                                       [dataSource]="data"
                                       xName="x"
                                       yName="y"
                                       [border]="border"
                                       [startAngle]="startAngle"
                                       innerRadius="65%"
                                       [radius]="radius"
                                       [dataLabel]="dataLabel">
                </e-accumulation-series>
            </e-accumulation-series-collection>
        </ejs-accumulationchart>
        <!-- <ejs-accumulationchart
            id="chart-container"
            [legendSettings]="legendSettings"
            width="300px"
            height="300px"
            align="center"
          >
            <e-accumulation-series-collection>
              <e-accumulation-series
                [dataSource]="piedata"
                xName="x"
                yName="y"
                innerRadius="40%"
              ></e-accumulation-series>
            </e-accumulation-series-collection> </ejs-accumulationchart
        > -->
    </dashboard-card-body>
    <!-- <div class="dashrows">
      <div class="dashrow">
        <div class="dashrow__title">Candidates Today</div>
        <div class="dashrow__figure">1</div>
      </div>
      <div class="dashrow">
        <div class="dashrow__title">Candidates This Month</div>
        <div class="dashrow__figure">15</div>
      </div>
      <div class="dashrow">
        <div class="dashrow__title">Candidates This Year</div>
        <div class="dashrow__figure">40</div>
      </div>
      <div class="dashrow">
        <div class="dashrow__title">Active Requisitions</div>
        <div class="dashrow__figure">5</div>
      </div>
      <div class="dashrow">
        <div class="dashrow__title">Published Requisitions</div>
        <div class="dashrow__figure">5</div>
      </div>
      <div class="dashrow">
        <div class="dashrow__title">In Progress Requisitions</div>
        <div class="dashrow__figure">5</div>
      </div>
    </div> -->
</div>