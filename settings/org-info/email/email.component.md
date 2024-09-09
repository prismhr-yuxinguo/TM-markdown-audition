<page-title [title]="'Email Settings'"></page-title>
<talent-footer
  [nextVisible]="false"
  [prevVisible]="false"
  (saveClicked)="save()"
  [saveEnabled]="saveEnabled"
  [saveVisible]="hasEdit"
></talent-footer>
<fieldset [formGroup]="orgInfoForm" [disabled]="!hasEdit">
  <settings-table>
    <settings-row
      title="Send E-mail Notifications?"
      description="Turn E-mail Notifications off/on"
      [required]="false"
    >
      <toggle-switch
        [form]="orgInfoForm"
        formControlName="emailNotification"
        [enabled]="hasEdit"
      ></toggle-switch>
    </settings-row>

    <settings-row
      title="Send All System E-mail Notifications to"
      [required]="true"
    >
      <ejs-multiselect
        id="multiselectelement"
        [value]="initialEmailValues"
        [dataSource]="emailsData"
        [allowCustomValue]="true"
        (tagging)="onTagging($event)"
        (removing)="onRemoving($event)"
        mode="Box"
        placeholder="Insert an email address..."
        [fields]="emailFields"
      ></ejs-multiselect>
      <p
        *ngIf="currentEmailValuesErrors() | async"
        class="error-message custom-error-message"
      >
        {{ currentEmailValuesErrors() | async }}
      </p>
    </settings-row>

    <settings-row
      title="Default E-mail Signature"
      description=""
      type="WYSIWYG"
    >
      <input-rich-text
        id="defaultRTE"
        [form]="orgInfoForm"
        [toolbarSettings]="editorTools"
        formControlName="signature"
        [enabled]="hasEdit"
      ></input-rich-text>
    </settings-row>
  </settings-table>
</fieldset>
