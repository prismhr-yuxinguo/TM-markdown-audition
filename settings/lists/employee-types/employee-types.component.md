<page-title [title]="'Employee Types'"></page-title>
<talent-grid #grid
             [allowBulkActions]="false"
             [allowFiltering]="false"
             [allowNew]="hasCreate"
             [allowRowSelect]="false"
             [data]="employeeTypes"
             exportFileName="EmployeeTypes"
             friendlyName="Employee Type"
             idProperty="typeId"
             [initializing]="initializing"
             [loading]="loading"
             [searchFields]="['description']"
             (selected)="selected($event)"
             [selectOptions]="selectOptions">
  <e-columns>
    <e-column field="description" headerText="Description">
      <ng-template *hasKey="[Keys.CoreEmployeeTypesEdit]" #template let-data>
        <ejs-tooltip #tooltip
                     [content]="editOrViewTooltip">
          <a class="grid-link disable-row-select" (click)="onLinkClicked($event, data)">{{ data.description }}</a>
        </ejs-tooltip>
      </ng-template>
    </e-column>
  </e-columns>
</talent-grid>

<!-- delete -->
<modal-base [config]="deleteModal" [template]="deleteContent"></modal-base>
<ng-template #deleteContent>
  <div class="row">
    <div class="col-xs-12">
      Are you sure you want to delete this employee type? Once deleted, it cannot be recovered.
    </div>
  </div>
</ng-template>

<!-- new / edit -->
<modal-base [config]="editSetupModal" [template]="editSetupContent"></modal-base>
<ng-template #editSetupContent>
  <settings-table>
    <settings-row [title]="'Description'" [description]="" [required]="true">
      <input-text [placeholder]="'Description'" [required]="true" [form]="employeeTypeFormGroup" formControlName="description"></input-text>
    </settings-row>
  </settings-table>
</ng-template>
