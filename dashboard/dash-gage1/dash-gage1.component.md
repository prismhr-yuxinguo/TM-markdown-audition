<ejs-circulargauge
  style="display: block"
  [width]="width"
  [height]="height"
  title="Summary"
  [titleStyle]="titleStyle"
  background="transparent"
>
  <e-axes>
    <e-axis
      startAngle="0"
      endAngle="270"
      minimum="0"
      maximum="100"
      [majorTicks]="ticks"
      [minorTicks]="ticks"
      [lineStyle]="lineStyle"
      [labelStyle]="labelStyle"
      [annotations]="annotations"
      [ranges]="ranges"
    >
      <e-pointers> </e-pointers>
    </e-axis>
  </e-axes>
</ejs-circulargauge>
