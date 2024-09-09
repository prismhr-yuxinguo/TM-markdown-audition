<talent-grid #grid 
    [allowFiltering]="false"
    [allowBulkActions]="false"
    [allowRowSelect]="false"
    [allowNew]="allowNew"
    [data]="requisitionStatusList" 
    [friendlyName]="'Requisition Status'"
    exportFileName="Requisition Statuses"
    [initializing]="initializing"
    (selected)="selected($event)"
    [selectActionTooltip]="selectActionTooltip"
    [selectOptions]="selectOptions"
    [searchFields]="['description']"
>
  <e-columns>
    <e-column field="description" headerText="Description">
      <ng-template *hasKey="[Keys.HiringRequisitionStatusesEdit]" #template let-data>
        <ejs-tooltip #tooltip
                     [content]="editOrViewTooltip">
          <a class="grid-link disable-row-select" (click)="onLinkClicked($event, data)">{{ data.description }}</a>
        </ejs-tooltip>
      </ng-template>
    </e-column>
  </e-columns>
</talent-grid>

 <!-- create edit modal -->
 <modal-base [config]="createEditRequisitionStatusModal" [template]="newTypeContent"></modal-base>
 <ng-template #newTypeContent [formGroup]="createEditRequisitionStatusForm">
   <settings-table>
     <settings-row [title]="'Description'" [description]="" [required]="true">
       <input-text [form]="createEditRequisitionStatusForm" formControlName="description" [placeholder]="'Description'"></input-text>
     </settings-row>
   </settings-table>
 </ng-template>
 
 
 <!-- delete modal -->
 <modal-base [config]="deleteRequisitionStatusModal" [template]="deleteContent"></modal-base>
 <ng-template #deleteContent>
   <div class="row">
     <div class="col-xs-12">
      Are you sure you want to delete this Requisition Status record? 
      Once deleted, it cannot be recovered.
     </div>
   </div>
 </ng-template>
