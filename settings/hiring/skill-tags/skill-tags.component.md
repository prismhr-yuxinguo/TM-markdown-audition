<page-title [title]="'Position Skill Tags'"></page-title>

<ejs-tab id="adaptiveTab" overflowMode="Popup"  (selected)="selected($event)" >
  <e-tabitems>
    <e-tabitem [header]="headerText[0]">
      <ng-template #content><app-tags></app-tags> </ng-template>
    </e-tabitem>
    <e-tabitem [header]="headerText[1]">
      <ng-template #content> <app-settings></app-settings></ng-template>
    </e-tabitem>
  </e-tabitems>
</ejs-tab>
