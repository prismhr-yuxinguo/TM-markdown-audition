<page-title [title]="'General Settings'"></page-title>

<ejs-tab id="adaptiveTab" overflowMode="Popup" (selected)="selected($event)">
  <e-tabitems>
    <e-tabitem [header]="headerText[0]">
      <ng-template #content
        ><talent-general-settings
          [activeTabIndex]="activeTabIndex"
        ></talent-general-settings>
      </ng-template>
    </e-tabitem>
  </e-tabitems>
</ejs-tab>
