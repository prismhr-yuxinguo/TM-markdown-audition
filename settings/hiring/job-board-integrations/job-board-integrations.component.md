<page-title [title]="'Job Board Integrations'"></page-title>

<talent-footer
  [nextVisible]="false"
  [prevVisible]="false"
  (saveClicked)="save()"
  [saveEnabled]="saveEnabled"
  [saveVisible]="isEditable"
>
</talent-footer>

<fieldset [formGroup]="hiringSettingForm">
  <settings-table>
    <settings-row [title]="'Indeed Integration'" [description]="'Include ALL Job Postings on Indeed'" [required]="">
      <toggle-switch [form]="hiringSettingForm" formControlName="indeedEnabled" [enabled]="isEditable"></toggle-switch>
    </settings-row>
  </settings-table>
</fieldset>
