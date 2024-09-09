<talent-grid #grid
  [allowFiltering]="false"
  [allowNew]="allowNew"
  [allowBulkActions]="false"
  [allowRowSelect]="false"
  [data]="candidateGroupsList"
  [friendlyName]="'Candidate Group'"
  exportFileName="Candidate Groups"
  [initializing]="initializing"
  (selected)="selected($event)"
  [selectActionTooltip]="selectActionTooltip" [selectOptions]="selectOptions"
  [searchFields]="['description']">
  <e-columns>
    <e-column field="description" headerText="Description">
      <ng-template *hasKey="[Keys.HiringCandidateGroupsEdit]" #template let-data>
        <ejs-tooltip #tooltip
                     [content]="editOrViewTooltip">
          <a class="grid-link disable-row-select" (click)="onLinkClicked($event, data)">{{ data.description }}</a>
        </ejs-tooltip>
      </ng-template>
    </e-column>
  </e-columns>
</talent-grid>

 <!-- create edit modal -->
 <modal-base [config]="createEditCandidateGroupModal" [template]="newTypeContent"></modal-base>
 <ng-template #newTypeContent [formGroup]="candidateGroupForm">
   <settings-table>
     <settings-row [title]="'Description'" [description]="" [required]="true">
       <input-text [form]="candidateGroupForm" formControlName="description" [placeholder]="'Description'"></input-text>
     </settings-row>
   </settings-table>
 </ng-template>
 
 
 <!-- delete modal -->
 <modal-base [config]="deleteCandidateGroupModal" [template]="deleteContent"></modal-base>
 <ng-template #deleteContent>
   <div class="row">
     <div class="col-xs-12">
      Are you sure you want to delete this Candidate Group record?
      Once deleted, it cannot be recovered.
     </div>
   </div>
 </ng-template>
