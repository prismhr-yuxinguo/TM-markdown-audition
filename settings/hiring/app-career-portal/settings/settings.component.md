<talent-footer
  [nextVisible]="false"
  [prevVisible]="false"
  (saveClicked)="save()"
  [saveVisible]="saveVisible"
  [saveEnabled]="saveEnabled"
></talent-footer>

<ng-container [formGroup]="appMessageSettingForm">
  <settings-table>
    <!--<settings-row
      [title]="'Display Job Alerts Section?'"
      [description]="'Allow candidates to sign up for job alerts/notifications of when you publish requisitions.'"
      [required]=""
    >
      <toggle-switch
        [form]="appMessageSettingForm"
        formControlName="allowJobAlerts"
      ></toggle-switch>
    </settings-row>-->
    <settings-row
      [title]="'Application and Career Messages'"
      [description]=""
      [required]=""
    >
      <input-dropdown
        [placeholder]="'Application and Career Messages'"
        [value]="1"
        (optionSelected)="changed($event)"
        [data]="messageList"
      ></input-dropdown>
    </settings-row>

    <fieldset [formGroup]="messageEditForm" id="custom_editor">
      <settings-row [title]="'Body '" [required]="currentMessageType == 'disclaimer' ? false : true" [type]="'WYSIWYG'">
        <input-rich-text
          id="messageBody"
          #messageBody
          [toolbarSettings]="editorTools"
          [height]="'300'"
          [form]="messageEditForm"
          formControlName="messageBody"
        ></input-rich-text>
        <p
          *ngIf="isValidationFailed"
          class="error-message custom-error-message"
        >
          {{ validationMessage }}
        </p>
      </settings-row>
    </fieldset>
  </settings-table>
</ng-container>
