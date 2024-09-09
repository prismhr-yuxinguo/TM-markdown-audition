<page-title [title]="'Application Templates'"></page-title>
<talent-grid #grid
             [allowNew]="allowNew"
             [allowRowSelect]="allowRowSelect"
             (applyFilters)="applyFilters($event)"
             (bulk)="bulk($event)"
             [bulkActionTooltip]="bulkActionTooltip"
             [bulkOptions]="bulkOptions"
             [data]="data"
             friendlyName="ApplicationTemplate"
             exportFileName="ApplicationTemplates"
             [filters]="filters"
             [filtersForm]="filtersForm"
             [initializing]="initializing"
             (initialized)="initialized($event)"
             [searchFields]="['candidateApplicationTemplateId', 'name']"
             (selected)="selected($event)"
             (filtersReset)="onClearFilter()"
             (rowSelected)="rowSelected($event)"
             [selectActionTooltip]="selectActionTooltip"
             [selectOptions]="getSelectOptions"
             idProperty="candidateApplicationTemplateId">
  <ng-template #filtersTemplate [formGroup]="filtersForm">
    <input-dropdown-multi [data]="templatesFilterItems"
                        [enableFiltering]="true"
                        [filtering]="templatesFilterFiltering"
                        [form]="filtersForm"
                        formControlName="templatesFilter"
                        mode="CheckBox"
                        ngDefaultControl
                        placeholder="Templates"
                        showSelectAll="true"
                        (optionsSelected)="templatesFilterOptionsSelected($event)"></input-dropdown-multi>
    <input-dropdown [data]="showArchiveFilterItems"
                    [form]="filtersForm"
                    formControlName="showArchiveFilter"
                    ngDefaultControl
                    placeholder="Show Archive"></input-dropdown>
  </ng-template>
  <e-columns> 
    <e-column field="candidateApplicationTemplateId" headerText="ID" width="150"></e-column>
    <e-column field="name" headerText="Template Name">
      <ng-template *hasKey="[Keys.HiringCandidateApplicationTemplatesView, Keys.HiringCandidateApplicationTemplatesEdit]" #template let-data>
        <ejs-tooltip #tooltip
                      [content]="editOrViewThisTemplate">
          <a class="grid-link disable-row-select" (click)="onLinkClicked($event, data)">{{ data.name }}</a>
        </ejs-tooltip>
      </ng-template>
    </e-column>
  </e-columns>
</talent-grid>
<!-- #confirmation -->
<modal-base [config]="confirmationPopupConfig" [template]="confirmationContent"></modal-base>
<ng-template #confirmationContent>
  <div class="row">
    <div class="col-xs-12">
      Are you sure you want to {{selectedAction}}?
    </div>
  </div>
</ng-template>
