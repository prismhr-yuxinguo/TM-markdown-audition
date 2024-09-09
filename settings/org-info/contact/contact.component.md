<page-title [title]="'Contact Information'"></page-title>
<talent-footer [nextVisible]="false"
               [prevVisible]="false"
               (saveClicked)="save()"
               [saveEnabled]="saveEnabled"
               [saveVisible]="hasEdit"></talent-footer>
<fieldset [formGroup]="orgInfoForm" [disabled]="!hasEdit">
  <settings-table>
    <settings-row [title]="'Phone'" [description]="" [required]="true">
      <input-phone [placeholder]="'Phone'"
                   [mask]="'(###) ###-####'"
                   [form]="orgInfoForm"
                   [required]="true"
                   formControlName="phone"></input-phone>
    </settings-row>
    <settings-row [title]="'Web Address'" [description]="" [required]="false">
      <input-text [placeholder]="'Web Address'" [required]="false" [form]="orgInfoForm" formControlName="webAddress"></input-text>
    </settings-row>
    <settings-row [title]="'Contact Email'" [description]="" [required]="true">
      <input-text [placeholder]="'Web Address'" [required]="true" [form]="orgInfoForm" formControlName="contactEmail"></input-text>
    </settings-row>

    <settings-row [title]="'Time Zone'" [description]="" [required]="true">
      <input-dropdown [data]="data"
                      [form]="orgInfoForm" formControlName="timeZoneId"
                      [placeholder]="'Choose Time Zone'"
                      [enableFiltering]="true"
                      [filtering]="true"
                      [required]="true"></input-dropdown>
    </settings-row>
  </settings-table>
</fieldset>
