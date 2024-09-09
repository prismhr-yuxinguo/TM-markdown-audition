<message-panel
[title]="'Display Order'"
[content]="'Reordering the Candidate Statuses changes the order of the statuses on the Candidate Detail and filters'"
></message-panel>
<talent-grid #grid
  [allowFiltering]="false"
  [allowBulkActions]="false"
  [allowPaging]="false"
  [allowRowDragAndDrop]="true"
  [allowRowSelect]="false"
  [allowSearch]="false"
  [allowSorting]="false"
  [allowNew]="allowNew"
  [data]="candidateStatusesList"
  [friendlyName]="'Candidate Status'"
  exportFileName="Candidate Statuses"
  [initializing]="initializing"
  (selected)="selected($event)"
  [selectActionTooltip]="selectActionTooltip" 
  [searchFields]="['candidateStatus','systemStatus','description']"
  (rowDrop)="onOrderChange($event)">
  <e-columns>
    <e-column field="candidateStatus" headerText="Interview Status" width="100px" [template]="candidateStatus" class="ellipsis"></e-column>
    <e-column field="systemStatus" headerText="System Status"></e-column>
    <e-column field="description" headerText="Description">
      <ng-template *hasKey="[Keys.HiringCandidateStatusesEdit]" #template let-data>
        <ejs-tooltip #tooltip
                     [content]="editOrViewTooltip">
          <a class="grid-link disable-row-select" (click)="onLinkClicked($event, data)">{{ data.description }}</a>
        </ejs-tooltip>
      </ng-template>
    </e-column> 
    <e-column
      field=""
      textAlign="center"
      [template]="dropdownactionbutton"
      width="80px"
    ></e-column>
  </e-columns>
</talent-grid>

<ng-template #candidateStatus let-data>
  <div class="btn-width" [ngClass]="'status__' + removeWhiteSpace(data.candidateStatus)">
    {{ data.candidateStatus }}
  </div>
</ng-template>

<ng-template #dropdownactionbutton let-data>
  <button-dropdown-grid
    [items]="!data.systemId ? editDeleteSelectOptions : editSelectOptions"
    [tooltip]="selectActionTooltip"
    (onSelect)="selected($event, data)"
  ></button-dropdown-grid>
</ng-template>

 <!-- create edit modal -->
 <modal-base [config]="createEditCandidateStatusModal" [template]="newTypeContent"></modal-base>
 <ng-template #newTypeContent [formGroup]="candidateStatusForm">
  <message-panel 
  [title]="'ATTENTION'"
  [state]="1"
  *ngIf="(infoMessage && ((candidateStatusForm.get('isAapInterview').value && isNewRecord) || !isNewRecord))"
  >
  <div>This is a system status: <span class="bold-text">{{infoMessage}}</span>. 
     You can edit the description text, but please be aware that it will still be used for
     all <span class="bold-text">{{infoMessage}}</span> related processes.</div>
</message-panel>
  
   <settings-table>
     <settings-row [title]="'Description'" [description]="" [required]="true">
       <input-text [form]="candidateStatusForm" formControlName="description" [placeholder]="'Description'"></input-text>
     </settings-row>
     <settings-row *ngIf="canAapInterview" [title]="'Interview Status'" [description]="">
      <toggle-switch  
      (check)="setInfoMessage()"
      [form]="candidateStatusForm" 
      formControlName="isAapInterview"
      floatLabelType="Always"
    ></toggle-switch>
    </settings-row>
   </settings-table>
 </ng-template>
 
 
 <!-- delete modal -->
 <modal-base [config]="deleteCandidateStatusModal" [template]="deleteContent"></modal-base>
 <ng-template #deleteContent>
   <div class="row">
     <div class="col-xs-12">
      Are you sure you want to delete this Candidate Status record? 
      Once deleted, it cannot be recovered.
     </div>
   </div>
 </ng-template>

<!-- unsaved changes modal -->
<modal-base [config]="unsavedChangesModal" [template]="unsavedChangesContent"></modal-base>
<ng-template #unsavedChangesContent>
  <div class="row">
    <div class="col-xs-12">
      {{ confirmationMessage}}
    </div>
  </div>
</ng-template>
