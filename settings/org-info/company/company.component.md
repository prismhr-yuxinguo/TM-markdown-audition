<page-title [title]="'Company Information'"></page-title>
<talent-footer [nextVisible]="false"
               [prevVisible]="false"
               (saveClicked)="save()"
               [saveEnabled]="saveEnabled"
               [saveVisible]="hasEdit"></talent-footer>
<fieldset [formGroup]="orgInfoForm" [disabled]="!hasEdit">
  <settings-table>
    <settings-row [title]="'Client Name'" [description]="" [required]="true">
      <input-text [placeholder]="'Client Name'" [required]="true" [form]="orgInfoForm" formControlName="clientName"></input-text>
    </settings-row>
    <settings-row [title]="'Address 1'" [description]="" [required]="true">
      <input-text [placeholder]="'Address 1'" [form]="orgInfoForm" formControlName="address1"></input-text>
    </settings-row>
    <settings-row [title]="'Address 2'" [description]="">
      <input-text [placeholder]="'Address 2'" [form]="orgInfoForm" formControlName="address2"></input-text>
    </settings-row>

    <settings-row [title]="'City'" [description]="" [required]="true">
      <input-text [placeholder]="'City'" [required]="true" [form]="orgInfoForm" formControlName="city"></input-text>
    </settings-row>

    <settings-row [title]="'State'" [description]="" [required]="true">
      <input-dropdown [data]="data"
                      [form]="orgInfoForm"
                      formControlName="stateCode"
                      [placeholder]="'State'"
                      [enableFiltering]="true"
                      [filtering]="true"
                      [required]="true"></input-dropdown>
    </settings-row>

    <settings-row [title]="'Zip Code'" [description]="" [required]="true">
      <ejs-maskedtextbox form="orgInfoForm" formControlName="maskedZipCode" mask="00000" placeholder="Zip Code" floatLabelType="Auto" required="true"></ejs-maskedtextbox>
      <p *ngIf="orgInfoForm.controls.maskedZipCode.invalid && orgInfoForm.controls.maskedZipCode.touched" class="error-message masked-value-error-message">
        Enter valid Zip Code
      </p>
    </settings-row>
  </settings-table>
</fieldset>
