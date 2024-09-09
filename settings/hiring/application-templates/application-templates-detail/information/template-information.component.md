<ng-template #infoTemplate>
  <ng-container [formGroup]="applicationTemplateForm">
    <ng-container formGroupName="information">
      <settings-table>
        <settings-row [title]="'Template Name'" [description]="" [required]="true">
          <input-text [form]="applicationTemplateForm.get('information')"
                      formControlName="name"
                      [required]="true"></input-text>
        </settings-row>

        <settings-row [title]="'Template Description'" [description]="">
          <input-multiline [form]="applicationTemplateForm.get('information')"
                           formControlName="description"></input-multiline>
        </settings-row>
      </settings-table>
    </ng-container>
  </ng-container>
</ng-template>

<fieldset *ngIf="!isEditable" disabled="disabled">
  <ng-container *ngTemplateOutlet="infoTemplate"></ng-container>
</fieldset>

<fieldset *ngIf="isEditable">
  <ng-container *ngTemplateOutlet="infoTemplate"></ng-container>
</fieldset>
