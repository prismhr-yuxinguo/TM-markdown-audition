<talent-footer
  [nextVisible]="false"
  [prevVisible]="false"
  (saveClicked)="save()"
  [saveEnabled]="true"
  [saveVisible]="true"
>
</talent-footer>

<ng-container [formGroup]="hiringSettingForm">
  <settings-table>
    <settings-row
      [title]="'Allow Requisition Routing?'"
      [description]="'Turn on/off job requisition approval routing.'"
      [required]=""
    >
      <toggle-switch
        [form]="hiringSettingForm"
        formControlName="requisitionApproval"
      ></toggle-switch>
    </settings-row>

    <div *ngIf="hiringSettingForm.get('requisitionApproval').value">
      <talent-grid
        #grid
        [allowNew]="true"
        [allowFiltering]="false"
        [allowBulkActions]="false"
        [allowPaging]="false"
        [allowRowDragAndDrop]="true"
        [allowSearch]="false"
        [allowRowSelect]="false"
        [allowSorting]="false"
        [allowAdditionalAction]="true"
        [additionalActionTitle]="additionalActionTitle"
        [additionalActionTooltip]="additionalActionTooltip"
        [data]="data"
        exportFileName="Requisition Approver"
        friendlyName="Requisition Approver"
        [initializing]="initializing"
        (selected)="selected($event)"
        [selectActionTooltip]="selectActionTooltip"
        [selectOptions]="selectOptions"
        (rowDrop)="onOrderChange($event)"
      >
        <e-columns>
          <e-column field="approverName" headerText="Approver Name"></e-column>
        </e-columns>
      </talent-grid>
    </div>
  </settings-table>
</ng-container>

<!-- delete -->
<modal-base
  [config]="confirmationPopupConfig"
  [template]="deleteContent"
></modal-base>
<ng-template #deleteContent>
  <div class="row">
    <div class="col-xs-12">
      {{ confirmationMessage }}
    </div>
  </div>
</ng-template>

<!-- Edit -->
<modal-base [config]="newSetupModal" [template]="editSetupContent"></modal-base>
<ng-template #editSetupContent>
  <ng-container [formGroup]="approverFormGroup">
    <settings-table>
      <settings-row
        [title]="'Requisition Approver'"
        [description]=""
        [required]="true"
      >
        <input-dropdown-multi
          [form]="approverFormGroup"
          formControlName="approversDropdown"
          [data]="requisitionApproverList"
          [mode]="'Box'"
          ngDefaultControl
          [required]="true"
        >
        </input-dropdown-multi>
      </settings-row>
    </settings-table>
  </ng-container>
</ng-template>
