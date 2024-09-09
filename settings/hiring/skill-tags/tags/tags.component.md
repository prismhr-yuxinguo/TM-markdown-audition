<talent-grid #grid
             [allowNew]="allowNew"
             [allowRowSelect]="allowRowSelect"
             (applyFilters)="applyFilters($event)"
             [allowBulkActions]="allowBulkActions"
             [data]="data"
             exportFileName="PositionSkillTags"
             [filters]="filters"
             [filtersForm]="filtersForm"
             friendlyName="Tag"
             [initializing]="initializing"
             (rowSelected)="rowSelected()"
             [searchFields]="['name']"
             (selected)="selected($event)"
             [selectActionTooltip]="selectActionTooltip"
             [selectOptions]="selectOptions">
  <ng-template #filtersTemplate [formGroup]="filtersForm">
    <input-dropdown [data]="showArchiveFilterItems"
                    [form]="filtersForm"
                    formControlName="showArchiveFilter"
                    ngDefaultControl
                    placeholder="Show Archive"></input-dropdown>
  </ng-template>
  <e-columns>
    <e-column field="name" headerText="Name">
      <ng-template *hasKey="[Keys.HiringSkillTagsEdit, Keys.HiringSkillTagsView]" #template let-data>
        <ejs-tooltip #tooltip
                     [content]="editOrViewThisTag">
          <a class="grid-link disable-row-select" (click)="onLinkClicked($event, data)">{{ data.name }}</a>
        </ejs-tooltip>
      </ng-template>
    </e-column>
  </e-columns>
</talent-grid>

<!-- delete -->
<modal-base [config]="confirmationPopupConfig" [template]="deleteContent"></modal-base>
<ng-template #deleteContent>
  <div class="row">
    <div class="col-xs-12">
      Are you sure you want to {{selectedAction}} this Tag?
    </div>
  </div>
</ng-template>

<!-- Edit -->
<modal-base [config]="editSetupModal"
            [template]="editSetupContent"></modal-base>
<ng-template #editSetupContent>
  <fieldset [formGroup]="tagFormGroup" [disabled]="!isEditable">
    <settings-table>
      <settings-row [title]="'Name'" [description]="" [required]="true">
        <input-text [placeholder]="'Name'" [required]="true" [form]="tagFormGroup" ngDefaultControl formControlName="name"></input-text>
      </settings-row>
      <settings-row [title]="'Synonyms '"
                    [description]="'Additional, similar words to match on when this tag is used'">
        <ejs-multiselect #muliselect
                         id='multiselectelement'
                         [value]="initialSynonymsValues"
                         [dataSource]="synonymData"
                         [allowCustomValue]='true'
                         (tagging)="onTagging($event)"
                         (removing)="onRemoving($event)"
                         mode='Box'
                         placeholder="Insert Synonyms"
                         [fields]="fields"></ejs-multiselect>
      </settings-row>
    </settings-table>
  </fieldset>
</ng-template>
