<dashboard-card-title [title]="'Summary'"></dashboard-card-title>
<style>
  .box-wrapper {
    display: flex;
    flex-wrap: wrap;
  }
  .box {
    color: white;
    padding: 8px;
    text-align: center;
  }
</style>
<dashboard-card-body>
  <div class="box-wrapper">
    <div class="box">
      <div>11</div>
      <div>Active Candidates</div>
    </div>
    <div class="box">
      <div>6</div>
      <div>Candidates today</div>
    </div>
    <div class="box">
      <div>6</div>
      <div>Candidates this month</div>
    </div>
    <div class="box">
      <div>6</div>
      <div>Candidates this year</div>
    </div>
  </div>
  <!-- <div class="pills">
    <div class="pill">6 Candidates this year</div>
    <div class="pill">6 Candidates this month</div>
  </div> -->
  <ejs-sparkline
    class="sparkline"
    height="100px"
    width="320px"
    lineWidth="2"
    valueType="Category"
    fill="var(--primary-white)"
    type="Area"
    negativePointColor="red"
    [border]="border"
    [dataSource]="aausData"
    [tooltipSettings]="areatooltipSettings"
    xName="xval"
    yName="yval"
  ></ejs-sparkline
></dashboard-card-body>
