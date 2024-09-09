<page-title [title]="'Resource Types'"></page-title>

<talent-grid #grid
             [allowBulkActions]="false"
             [allowFiltering]="false"
             [allowNew]="hasCreate"
             [allowRowSelect]="false"
             [data]="resourceTypes"
             exportFileName="ResourceTypes"
             friendlyName="ResourceTypes"
             [searchFields]="['description', 'code']"
             (selected)="selected($event)"
             [selectOptions]="selectOptions">
  <e-columns>
    <e-column field="description" headerText="Description"></e-column>
    <e-column field="moduleName" headerText="Module Name"></e-column>
  </e-columns>
</talent-grid>

<!-- delete -->
<modal-base [config]="deleteModal" [template]="deleteContent"></modal-base>
<ng-template #deleteContent>
  <div class="row">
    <div class="col-xs-12">
      Are you sure you want to delete this Respurce Type? Once deleted, it cannot be recovered.
    </div>
  </div>
</ng-template>

<!-- new / edit -->
<modal-base [config]="editSetupModal"
            [template]="editSetupContent"></modal-base>
<ng-template #editSetupContent>
  <settings-table>
    <settings-row [title]="'Description'" [description]="" [required]="true">
      <input-text [placeholder]="'Description'" [required]="true" [form]="resourceTypeFormGroup" formControlName="description"></input-text>
    </settings-row>
    <settings-row [title]="'Module'">
      <input-dropdown [form]="resourceTypeFormGroup"
                      formControlName="module"
                      [data]="moduleDropDownData"
                      placeholder="Select a Respurce Type"
                      [enableFiltering]="false"
                      [enabled]="true"
                      [floatLabelType]="'Never'"
                      [required]="required"></input-dropdown>
    </settings-row>
  </settings-table>
</ng-template>
