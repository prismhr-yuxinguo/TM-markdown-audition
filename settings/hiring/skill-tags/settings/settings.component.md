<talent-footer
  [nextVisible]="false"
  [prevVisible]="false"
  (saveClicked)="save()"
  [saveEnabled]="true"
  [saveVisible]="isEditable"
>
</talent-footer>

<fieldset [formGroup]="tagSettingForm">
  <settings-table>
    <settings-row [title]="'Allow New Tags on Position '"
                  [description]="'Not from this library'"
                  [required]="false">
      <toggle-switch [form]="tagSettingForm"
                     formControlName="canAddNewJobSkillTag"
                     [enabled]="isEditable"></toggle-switch>
    </settings-row>
    <settings-row [title]="'Add New Tags from Position into this Library'"
                  [required]="false">
      <toggle-switch [form]="tagSettingForm"
                     formControlName="canAddNewJobSkillTagToLibrary"
                     [enabled]="isEditable"></toggle-switch>
    </settings-row>
    <settings-row [title]="'Allow New Tags on Requisition'"
                  [description]="'Not from the Position Library'"
                  [required]="false">
      <toggle-switch [form]="tagSettingForm"
                     formControlName="canAddNewReqSkillTag"
                     [enabled]="isEditable"></toggle-switch>
    </settings-row>
    <settings-row [title]="'Add New Tags from Requisition into the Position Library'"
                  [required]="false">
      <toggle-switch [form]="tagSettingForm"
                     formControlName="canAddNewReqSkillTagToLibrary"
                     [enabled]="isEditable"></toggle-switch>
    </settings-row>
    <settings-row [title]="'Allow Deletion of Tags on Requisition'"
                  [required]="false">
      <toggle-switch [form]="tagSettingForm"
                     formControlName="canDeleteReqSkillTag"
                     [enabled]="isEditable"></toggle-switch>
    </settings-row>
  </settings-table>
</fieldset>
