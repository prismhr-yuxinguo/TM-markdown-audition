<div class="modal-drawer__head">
  {{ emailTemplateHeading }}
  <div class="modal-drawer__cta">
    <button-base [title]="'Cancel'"
                 [isPrimary]="false"
                 (onClick)="ClosePopup()"></button-base>
    <button-base *ngIf="!isViewOnly"
                 [title]="'Save'"
                 [isPrimary]="true"
                 (click)="saveEmailTemplate()"
                 [visible]="!isSaving"></button-base>
  </div>
</div>
<div class="card card--split" [formGroup]="emailTemplateForm">
  <div class="split__col">
    <settings-table>
      <settings-row [title]="'Name'" [required]="true" *ngIf="!isSystemCreated || isNew">
        <input-text [form]="emailTemplateForm" formControlName="name" [required]="true">
        </input-text>
      </settings-row>
      <settings-row [title]="'Subject'" [required]="true">
        <input-text [placeholder]="'Subject'" [form]="emailTemplateForm" formControlName="subject" [required]="true">
        </input-text>
      </settings-row>
      <settings-row [title]="'Email Message'"
                    [required]="true"
                    [type]="'WYSIWYG'">
        <input-rich-text id="defaultRTE"
                         cssClass="rte-override"
                         (created)='onCreate()'
                         [form]="emailTemplateForm"
                         formControlName="emailMessage"
                         [toolbarSettings]="editorTools"></input-rich-text>
      </settings-row>
      <settings-row [title]="'Attachment'"
                    [description]="'Accepted file types: pdf, doc, docx, txt | Max size: 3MB'"
                    *ngIf="!isSystemCreated || isNew">
        <div class="offer-letter__name" *ngIf="emailTemplateForm.controls.attachments.value">
          <i class="fa-solid fa-paperclip"></i>
          <span style="font-weight: 600;">Attachment:</span> {{emailTemplateForm.controls.attachments.value}}
          <i class="fa-solid fa-trash custom-cursor" (click)="clearFile(fileInput)"></i>
        </div>
        <input #fileInput
               type="file"
               (change)="handleUpload($event)"
               accept=".pdf, .doc, .docx, .txt"
               class="custom-file-input"
               [disabled]="isFileInputDisabled">

      </settings-row>
      <settings-row [title]="'Template Use'"
                    *ngIf="!isSystemCreated || isNew"
                    [description]="'Sets the way this template is used: General, Candidate Status or Candidate Dismissal'">
        <input-dropdown [data]="templateUseList"
                        [placeholder]="'Template Use'"
                        [form]="emailTemplateForm"
                        formControlName="templateUse"
                        (optionSelected)="onDropDownChange($event)"></input-dropdown>
      </settings-row>
      <settings-row [title]="'Status'" [required]="true" *ngIf="emailTemplateForm.get('templateUse').value === 'candidateStatus'">
        <input-dropdown-multi (optionsSelected)="setTemplateUseValues($event)"
                              [form]="emailTemplateForm"
                              formControlName="status"
                              [data]="candidateStatusesList"
                              [enableFiltering]="true"
                              mode="CheckBox"
                              ngDefaultControl
                              showSelectAll="true"
                              placeholder="Status"></input-dropdown-multi>

      </settings-row>
      <settings-row [title]="'Dismissal'" [required]="true" *ngIf="emailTemplateForm.get('templateUse').value === 'candidateDismissal'">
        <input-dropdown-multi (optionsSelected)="setTemplateUseValues($event)"
                              [form]="emailTemplateForm"
                              formControlName="dismissal"
                              [data]="dismissalReasonsList"
                              [enableFiltering]="true"
                              mode="CheckBox"
                              ngDefaultControl
                              showSelectAll="true"
                              placeholder="Dismissal"></input-dropdown-multi>
      </settings-row>
    </settings-table>

  </div>
  <div class="split__col offer-letter">
    <div class="offer-letter__title" style="align-self: center;">Email Preview</div>
    <div class="offer-letter__body">
      <div class="offer-letter__body-title">
        <div class="offer-letter__name"><span style="font-weight: 600;">To:</span> {{emailTemplateForm.controls.name.value}}</div>
        <br />
        <div class="offer-letter__name"><span style="font-weight: 600;">Email Subject:</span> {{emailTemplateForm.controls.subject.value}}</div>
        <br />
        <div class="offer-letter__name"><span style="font-weight: 600;">Attachment:</span> {{emailTemplateForm.controls.attachments.value}}</div>
        <br />
      </div>
      <div class="offer-letter__message">
        <div class="viewing-First-Candidate"> You are currently viewing the first candidate in the mailing list.</div>
        <div class="disabled" [innerHTML]="previewHtml"></div>
      </div>
    </div>

  </div>
</div>
