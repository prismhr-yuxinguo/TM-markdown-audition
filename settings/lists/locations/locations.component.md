<page-title [title]="'Locations'"></page-title>
<talent-loading [loading]="loading"></talent-loading>
<talent-grid #grid
             [allowBulkActions]="false"
             [allowFiltering]="false"
             [allowNew]="!isSyncEnabled && hasCreate"
             [allowRowSelect]="false"
             [data]="locations"
             exportFileName="Locations"
             friendlyName="Location"
             idProperty="typeId"
             [initializing]="initializing"
             [searchFields]="['locationName', 'physicalLocation', 'email', 'countryCode', 'phoneNumber']"
             (selected)="selected($event)"
             [selectOptions]="selectOptions">
  <e-columns>
    <e-column *ngIf="isHcmSync" field="" headerText="" width="80">
      <ng-template #template let-data>
        <div class="status__blocks">
          <ejs-tooltip *ngIf="data.locationCode" #tooltip content="Synced from HCM">
            <i class="status__base status__small-block fa-regular fa-rotate"></i>
          </ejs-tooltip>
        </div>
      </ng-template>
    </e-column>
    <e-column field="locationName" headerText="Location Name">
      <ng-template *hasKey="[Keys.CoreLocationsEdit]" #template let-data>
        <ejs-tooltip #tooltip
                     [content]="editOrViewTooltip">
          <a class="grid-link disable-row-select" (click)="onLinkClicked($event, data)">{{ data.locationName }}</a>
        </ejs-tooltip>
      </ng-template>
    </e-column>
    <e-column field="physicalLocation" headerText="Physical Location"></e-column>
    <e-column field="email" headerText="Email"></e-column>
    <e-column field="countryCode" headerText="Country Code"></e-column>
    <e-column field="phoneNumber" headerText="Phone"></e-column>
    <e-column field="locationCode" headerText="Payroll Code" *hasPayrollIntegration="prism"></e-column>
  </e-columns>
</talent-grid>

<!-- delete -->
<modal-base [config]="deleteModal" [template]="deleteContent"></modal-base>
<ng-template #deleteContent>
  <div class="row">
    <div class="col-xs-12">
      Are you sure you want to delete this Location? Once deleted, it
      cannot be recovered.
    </div>
  </div>
</ng-template>

<!-- new/edit -->
<modal-base [config]="editSetupModal"
            [template]="editSetupContent"></modal-base>
<ng-template #editSetupContent>
  <ng-container [formGroup]="locationFormGroup">
    <settings-table>
      <settings-row [title]="'Location Name'" [description]="" [required]="true">
        <input-text [placeholder]="'Location Name'"
                    [required]="true" [form]="locationFormGroup" formControlName="locationName"></input-text>
      </settings-row>
      <settings-row [title]="'Country Code'" [description]="" [required]="true">
        <input-dropdown [form]="locationFormGroup"
                        formControlName="countryCode"
                        [data]="countries"
                        placeholder="Select a Country"
                        [enableFiltering]="false"
                        [enable]="false"
                        [floatLabelType]="'Never'"
                        [validation]="{'required': false}"></input-dropdown>
      </settings-row>
      <settings-row [title]="'City'" [description]="" [required]="true">
        <input-text [placeholder]="'City'" [required]="true" [form]="locationFormGroup" formControlName="city"></input-text>
      </settings-row>
      <settings-row [title]="'State'" [description]="" [required]="true">
        <input-dropdown [form]="locationFormGroup"
                        formControlName="state"
                        [data]="states"
                        placeholder="Select a State"
                        [enableFiltering]="false"
                        [enabled]="true"
                        [floatLabelType]="'Never'"
                        [required]="required"></input-dropdown>
      </settings-row>
      <settings-row [title]="'Zip Code'" [description]="" [required]="true">
        <ejs-maskedtextbox form="locationFormGroup" formControlName="maskedZipCode" mask="00000" placeholder="Zip Code" floatLabelType="Auto" required="true"></ejs-maskedtextbox>
        <p *ngIf="locationFormGroup.controls.maskedZipCode.invalid && locationFormGroup.controls.maskedZipCode.touched" class="error-message masked-value-error-message">
          This field is required
        </p>
      </settings-row>
      <settings-row [title]="'Email'" [description]="">
        <input-text [placeholder]="'Email'" [form]="locationFormGroup" formControlName="email"></input-text>
      </settings-row>

      <settings-row [title]="'Phone'" [description]="">
        <input-phone [placeholder]="'Phone'"
                     [mask]="'(###) ###-####'" [form]="locationFormGroup" formControlName="phoneNumber"></input-phone>
      </settings-row>
      <ng-container *hasPayrollIntegration="prism">
        <settings-row [title]="'Payroll Code'" [description]="">
          <input-text [placeholder]="'Payroll Code'"></input-text>
        </settings-row>
      </ng-container>
    </settings-table>
  </ng-container>
</ng-template>

<!-- merge -->
<modal-base [config]="mergeModal"
            [template]="mergeContent"></modal-base>
<ng-template #mergeContent>
  <settings-table [formGroup]="mergeRequest">
    <settings-row [title]="'Source Location'" [description]="'Will be deleted.'" [required]="true">
      <input [value]="locationFormGroup.controls.locationName.value" class="e-input search-bar" disabled />
    </settings-row>
    <settings-row [title]="'Target Location'" [description]="'All records will be reassigned to.'" [required]="true">
      <input-dropdown [data]="mergeDropdownData" [placeholder]="'Select a Location'" [enableFiltering]="false" [required]="true" [form]="mergeRequest" formControlName="targetId"></input-dropdown>
    </settings-row>
  </settings-table>
</ng-template>

<modal-base [config]="mergeWarningModal"
            [template]="mergeWarning"></modal-base>
<ng-template #mergeWarning>
  <settings-table>
    <h1>
      This will move all employees and requisitions at the selected location into the new designated location.
      This <b>CAN NOT</b> be undone. Are you sure you want to continue?
    </h1>
  </settings-table>
</ng-template>
