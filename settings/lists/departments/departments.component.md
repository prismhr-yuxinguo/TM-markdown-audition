<page-title [title]="'Departments'"></page-title>
<talent-loading [loading]="loading"></talent-loading>
<talent-grid #grid
             [allowBulkActions]="false"
             [allowFiltering]="false"
             [allowNew]="!isSyncEnabled && hasCreate"
             [allowRowSelect]="false"
             [data]="departments"
             exportFileName="Departments"
             friendlyName="Department"
             idProperty="typeId"
             [initializing]="initializing"
             [searchFields]="['description', 'code']"
             (selected)="selected($event)"
             [selectOptions]="selectOptions">
  <e-columns>
    <e-column *ngIf="isHcmSync" field=""
              headerText=""
              width="80">
      <ng-template #template let-data>
        <div class="status__blocks">
          <ejs-tooltip *ngIf="data.code"
                       #tooltip
                       content="Synced from HCM">
            <i class="status__base status__small-block fa-regular fa-rotate"></i>
          </ejs-tooltip>
        </div>
      </ng-template>
    </e-column>
    <e-column field="description" headerText="Description">
      <ng-template *hasKey="[Keys.CoreDepartmentsEdit]" #template let-data>
        <ejs-tooltip #tooltip
                     [content]="editOrViewTooltip">
          <a class="grid-link disable-row-select" (click)="onLinkClicked($event, data)">{{ data.description }}</a>
        </ejs-tooltip>
      </ng-template>
    </e-column>
    <e-column *hasPayrollIntegration="prism" field="code" headerText="Payroll Code"></e-column>
  </e-columns>
</talent-grid>

<!-- delete -->
<modal-base [config]="deleteModal" [template]="deleteContent"></modal-base>
<ng-template #deleteContent>
  <div class="row">
    <div class="col-xs-12">
      Are you sure you want to delete this Department? Once deleted, it cannot be recovered.
    </div>
  </div>
</ng-template>

<!-- new / edit -->
<modal-base [config]="editSetupModal"
            [template]="editSetupContent"></modal-base>
<ng-template #editSetupContent>
  <settings-table>
    <settings-row [title]="'Description'" [description]="" [required]="true">
      <input-text [placeholder]="'Description'" [required]="true" [form]="departmentFormGroup" formControlName="description"></input-text>
    </settings-row>
    <settings-row *hasPayrollIntegration="prism" title="Payroll Code" description="" [required]="false">
      <input-text placeholder="Payroll Code"></input-text>
    </settings-row>
  </settings-table>
</ng-template>

<!-- merge -->
<modal-base [config]="mergeModal"
            [template]="mergeContent"></modal-base>
<ng-template #mergeContent>
  <settings-table [formGroup]="mergeModalForm">
    <settings-row [title]="'Source Department'" [description]="'Will be deleted.'" [required]="true">
      <input [value]="departmentFormGroup.controls.description.value" class="e-input search-bar" disabled />
    </settings-row>
    <settings-row [title]="'Target Department'" [description]="'All records will be reassigned to.'" [required]="true">
      <input-dropdown [data]="mergeDropdownData" [value]="value" [placeholder]="'Select a Department'" [enableFiltering]="false" [required]="true" [form]="mergeModalForm" formControlName="targetId"></input-dropdown>
    </settings-row>
  </settings-table>
</ng-template>

<modal-base [config]="mergeWarningModal"
            [template]="mergeWarning"></modal-base>
<ng-template #mergeWarning>
  <settings-table>
    <h1>
      This will move all employees and requisitions assigned to the selected department into the new designated department.
      This <b>CAN NOT</b> be undone. Are you sure you want to continue?
    </h1>
  </settings-table>
</ng-template>
