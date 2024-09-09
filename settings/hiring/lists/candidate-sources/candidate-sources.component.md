

<talent-grid #grid
             [allowFiltering]="false"
             [allowBulkActions]="false"
             [allowRowSelect]="false"
             [allowNew]="allowNew"
             [data]="jscListData"
             [friendlyName]="'Job Source Channel'"
             exportFileName="Job Source Channels"
             [initializing]="initializing"
             (selected)="selected($event)"
             [selectActionTooltip]="selectActionTooltip"
             [selectOptions]="selectOptions"
             [searchFields]="['name','description']"
             >
  <e-columns>
    <e-column field="name" headerText="Name">
      <ng-template *hasKey="[Keys.HiringCandidateSourcesEdit]" #template let-data>
        <ejs-tooltip #tooltip
                     [content]="editOrViewTooltip">
          <a class="grid-link disable-row-select" (click)="onLinkClicked($event, data)">{{ data.name }}</a>
        </ejs-tooltip>
      </ng-template>
    </e-column>
    <e-column field="description" headerText="Description"></e-column>
  </e-columns>
</talent-grid>

<!-- Add New Job Source Channel Modal  -->
<modal-base [config]="createEditJobSrcChannelModal" [template]="newTypeContent"></modal-base>
  <ng-template #newTypeContent [formGroup]="createEditJobSourceChannelFormGroup">
    <settings-table>
      <settings-row [title]="'Name'" [description]="" [required]="true">
        <input-text [form]="createEditJobSourceChannelFormGroup" formControlName="name" [placeholder]="'Name'" [required]="true"></input-text>
      </settings-row>
      <settings-row [title]="'Description'" [description]="" [required]="true">
        <input-text [form]="createEditJobSourceChannelFormGroup" formControlName="description" [placeholder]="'Description'" [required]="true"></input-text>
      </settings-row>
    </settings-table>
  </ng-template>

<!-- delete -->
<modal-base [config]="deleteJobSrcChannelModal" [template]="deleteContent"></modal-base>
 <ng-template #deleteContent>
    <div class="row">
      <div class="col-xs-12">
        Are you sure you want to delete this Job Source Channel? Once deleted, it cannot be recovered.
      </div>
    </div>
  </ng-template>
