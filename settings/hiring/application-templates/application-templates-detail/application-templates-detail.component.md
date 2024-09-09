<page-title [title]="pageTitle"></page-title>

<talent-footer
  [nextVisible]="nextEnabled"
  [prevVisible]="prevEnabled"
  (prevClicked)="prevClicked()"
  (nextClicked)="nextClicked()"
  [saveEnabled]="saveEnabled"
  (saveClicked)="saveForm()"
  [saveVisible]="saveVisible"
></talent-footer>

<ejs-tab #tab id="adaptiveTab" overflowMode="Popup">
  <e-tabitems>
    <e-tabitem [header]="tabHeadings[0]">
      <ng-template #content>
        <app-application-templates-detail-information></app-application-templates-detail-information>
      </ng-template>
    </e-tabitem>
    <e-tabitem [header]="tabHeadings[1]">
      <ng-template #content
        ><app-application-templates-detail-definition></app-application-templates-detail-definition
      ></ng-template>
    </e-tabitem>
  </e-tabitems>
</ejs-tab>

<modal-base
  [config]="unsavedChangesModal"
  [template]="unsavedChangesContent"
></modal-base>

<ng-template #unsavedChangesContent>
  <div class="row">
    <div class="col-xs-12">
      <span [innerHTML]="confirmationMessage"></span>
    </div>
  </div>
</ng-template>
