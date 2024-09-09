<page-title [title]="'Position Classifications'"></page-title>
<talent-loading [loading]="loading"></talent-loading>
<talent-grid #grid
             [allowBulkActions]="false"
             [allowFiltering]="false"
             [allowNew]="!isSyncEnabled && hasCreate"
             [allowRowSelect]="false"
             [data]="classifications"
             exportFileName="Classifications"
             friendlyName="Classification"
             idProperty="typeId"
             [initializing]="initializing"
             [searchFields]="['description']"
             (selected)="selected($event)"
             [selectOptions]="selectOptions">
  <e-columns>
    <e-column field="description" headerText="Description">
      <ng-template *hasKey="[Keys.CorePositionClassificationsEdit]" #template let-data>
        <ejs-tooltip #tooltip
                     [content]="editOrViewTooltip">
          <a class="grid-link disable-row-select" (click)="onLinkClicked($event, data)">{{ data.description }}</a>
        </ejs-tooltip>
      </ng-template>
    </e-column>
    <e-column *hasPayrollIntegration field="code" headerText="Payroll Code"></e-column>
  </e-columns>
</talent-grid>

<!-- delete -->
<modal-base [config]="deleteModal" [template]="deleteContent"></modal-base>
<ng-template #deleteContent>
  <div class="row">
    <div class="col-xs-12">
      Are you sure you want to delete this position classification? Once deleted, it cannot be recovered.
    </div>
  </div>
</ng-template>

<!-- new / edit -->
<modal-base [config]="editSetupModal"
            [template]="editSetupContent"></modal-base>
<ng-template #editSetupContent>
  <settings-table>
    <settings-row [title]="'Description'" [description]="" [required]="true">
      <input-text [placeholder]="'Description'" [required]="true" [form]="classificationFormGroup" formControlName="description"></input-text>
    </settings-row>
    <ng-container *hasPayrollIntegration>
      <settings-row [title]="'Payroll Code'" [description]="" [required]="">
        <input-text [placeholder]="'Payroll Code'" [form]="classificationFormGroup" formControlName="code"></input-text>
      </settings-row>
    </ng-container>
  </settings-table>
</ng-template>

<!-- merge -->
<modal-base [config]="mergeModal"
            [template]="mergeContent"></modal-base>
<ng-template #mergeContent>
  <settings-table  [formGroup]="mergeModalForm">
    <settings-row [title]="'Source Classification'" [description]="'Will be deleted.'" [required]="true">
      <input [value]="classificationFormGroup.controls.description.value" class="e-input search-bar" disabled />
    </settings-row>
    <settings-row [title]="'Target Classification'" [description]="'All records will be reassigned to.'" [required]="true">
      <input-dropdown [data]="mergeDropdownData" [value]="value" [placeholder]="'Select a Classification'" [enableFiltering]="false" [required]="true" [form]="mergeModalForm" formControlName="targetId"></input-dropdown>
    </settings-row>
  </settings-table>
</ng-template>

<modal-base [config]="mergeWarningModal"
            [template]="mergeWarning"></modal-base>
<ng-template #mergeWarning>
  <settings-table>
    <h1>
      This will move all positions assigned to the selected Position
      Classification into the new designated Position Classification.
      This <b>CAN NOT</b> be undone. Are you sure you want to continue?
    </h1>
  </settings-table>
</ng-template>
