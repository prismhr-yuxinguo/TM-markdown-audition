<div class="dashboard__card"  [formGroup]="filtersForm"  #customCard>
  <dashboard-card-title [title]="'Active Candidates'">
      <input-dropdown 
                      [form]="filtersForm"
                      formControlName="requisitions"
                      [data]="requisitionsData"
                      [placeholder]="'Choose Requisition'"
                      [floatLabelType]="'Never'"
                      (optionSelected)="onDropDownChange($event)"
                      ></input-dropdown>
  </dashboard-card-title>
  <dashboard-card-body>
  <div id="custom-grid">
  <talent-grid
    #grid
    [allowSorting]="true"
    [allowPaging]="true"
    [allowNew]="false"
    [allowFiltering]="false"
    [allowBulkActions]="false"
    [allowSearch]="false"
    [allowExport]="false"
    [gridHeight]="customGridHeight"
    [data]="candidatesListData"
    (initialized)="initialized($event)"
    (selected)="selected($event)"
    (dataStateChange)="dataStateChange($event)"
    [selectOptions]="selectOptions"
    [loading]="loading"
    [isServerSide]="false"    
  >
  <e-columns>
      <e-column field="fullNameLastFirst" headerText="Candidate">
          <ng-template #template let-data>
              <ejs-tooltip *hasKey="[Keys.HiringCandidatesView, Keys.HiringCandidatesEdit]"   #tooltip
                           [content]="editOrViewThisCandidate + ' (' + data.fullNameLastFirst + ')'">
                <a class="grid-link disable-row-select" (click)="onLinkClicked($event, data)">{{ data.fullNameLastFirst }}</a>
              </ejs-tooltip>
            </ng-template>
      </e-column>
      <e-column field="candidateStatus" headerText="Status"></e-column>
  </e-columns>
  </talent-grid>
</div>
  </dashboard-card-body>
</div>
