<div class="modal-drawer__head">
  {{ offerLetterHeading }}
  <div class="modal-drawer__cta">
    <button-base [title]="'Cancel'"
                 [isPrimary]="false"
                 (onClick)="closeModalEmit()"></button-base>
    <button-base [title]="'Save'"
                 (onClick)="saveLetter()"
                 [visible]="isEditable"></button-base>
  </div>
</div>
<div class="card card--split">
  <div class="split__col">
    <fieldset [formGroup]="offerLetterForm" [disabled]="!isEditable">
      <settings-table>
        <settings-row [title]="'Letter Name'" [description]="" [required]="true">
          <input-text [placeholder]="'Letter Name'"
                      [required]="true"
                      [form]="offerLetterForm"
                      formControlName="letterName"></input-text>
        </settings-row>
        <settings-row [title]="'Letter Body'"
                      [description]=""
                      [required]="true"
                      [type]="'WYSIWYG'">
          <input-rich-text [height]="480"
                           (created)="onCreate()"
                           [form]="offerLetterForm"
                           formControlName="letterContent"
                           [toolbarSettings]="editorTools"></input-rich-text>

        </settings-row>
        <p class="error-message" *ngIf="showLetterContentError" style="margin-top: -20px; margin-left: 20px;">
          <span [innerText]="'This field is required'"></span>
        </p>
      </settings-table>
    </fieldset>
  </div>
  <div class="split__col offer-letter">
    <div class="offer-letter__title" style="align-self: center;">Offer Letter Preview</div>
    <div class="offer-letter__body">
      <div class="offer-letter__message">
        <div class="disabled" [innerHTML]="previewHtml"></div>
      </div>
    </div>
  </div>
</div>
