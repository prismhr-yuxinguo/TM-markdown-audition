<page-title [title]="'Email Templates'"></page-title>
<talent-grid #grid
             [allowBulkActions]="false"
             [allowFiltering]="true"
             [allowNew]="allowNew"
             [allowNewDisabled]="allowNewDisabled"
             [allowRowSelect]="false"
             (applyFilters)="applyFilters($event)"
             [data]="emailTemplatesList"
             exportFileName="Email Templates"
             [filters]="filters"
             [filtersForm]="filtersForm"
             [friendlyName]="'Email Template'"
             [initializing]="initializing"
             [loading]="loading"
             (rowSelected)="rowSelected()"
             [searchFields]="['templateName', 'module', 'type', 'subject', 'trigger', 'triggerCondition']"
             [selectActionTooltip]="selectActionTooltip"
             (selected)="selected($event)">
  <ng-template #filtersTemplate [formGroup]="filtersForm">
    <!-- TODO: Un-comment once need to apply module filter -->
    <!-- <input-dropdown-multi
      [data]="moduleFilterItems"
      [enableFiltering]="true"
      [filtering]="moduleFilterFiltering"
      [form]="filtersForm"
      formControlName="moduleFilter"
      mode="CheckBox"
      ngDefaultControl
      placeholder="Module"
      showSelectAll="true"
    ></input-dropdown-multi> -->
    <input-dropdown-multi [data]="typeFilterItems"
                          [enableFiltering]="true"
                          [filtering]="typeFilterFiltering"
                          [form]="filtersForm"
                          formControlName="typeFilter"
                          mode="CheckBox"
                          ngDefaultControl
                          placeholder="Type"
                          showSelectAll="true"                          
                          (optionsSelected)="typeFilterOptionsSelected($event)"
                          ></input-dropdown-multi>
    <input-dropdown [data]="showArchiveFilterItems"
                    [form]="filtersForm"
                    formControlName="showArchiveFilter"
                    ngDefaultControl
                    placeholder="Show Archive"></input-dropdown>

  </ng-template>
  <e-columns>
    <e-column field="templateName" headerText="Template Name">
      <ng-template *hasKey="[Keys.CoreEmailTemplatesView, Keys.CoreEmailTemplatesEdit]" #template let-data>
        <ejs-tooltip #tooltip
                     [content]="editOrViewTooltip">
          <a class="grid-link disable-row-select" (click)="onLinkClicked($event, data)">{{ data.templateName }}</a>
        </ejs-tooltip>
      </ng-template>
    </e-column>
    <e-column field="module" headerText="Module" [valueAccessor]="moduleValueAccessor"></e-column>
    <e-column field="type" headerText="Type"></e-column>
    <e-column field="subject" headerText="Subject"></e-column>
    <e-column field="trigger" headerText="Trigger"></e-column>
    <e-column field="triggerCondition" headerText="Trigger Condition"></e-column>
    <e-column field=""
              textAlign="center"
              [template]="dropdownActionbutton"
              width="80px"></e-column>
  </e-columns>
</talent-grid>

<modal-base
  [config]="archievePopupConfig"
  [template]="archievePopupContent"
></modal-base>
<ng-template #archievePopupContent>
  <div class="row">
    <div class="col-xs-12">
      Are you sure you want to Archive this Email Template?
    </div>
  </div>
</ng-template>

<modal-base
  [config]="unarchievePopupConfig"
  [template]="unarchievePopupContent"
></modal-base>
<ng-template #unarchievePopupContent>
  <div class="row">
    <div class="col-xs-12">
      Are you sure you want to Unarchive this Email Template?
    </div>
  </div>
</ng-template>

<ng-template #dropdownActionbutton let-data>
  <button-dropdown-grid 
    [items]="data.isSystem ? data.selectOptions : data.dropOptions"
    [tooltip]="selectActionTooltip"
    (onSelect)="selected($event, data)"
  ></button-dropdown-grid>
</ng-template>

<modal-drawer 
 [open]="showEmailPopup"
 [showButton]="false" 
 [template]="addEditEmailTemplate">
</modal-drawer>
<ng-template #addEditEmailTemplate>
  <talent-new-edit-email-template 
  (closeModal)="closeEmailPopup($event)"
  (refreshList)="getAllEmailTemplates()"
  [isNew]="isNewRecord"
  [isViewOnly]="isViewOnly"
  [selectedEmailTemplate]="selectedEmailTemplate"
  [isSystemCreated]="selectedEmailTemplate?.isSystem ? true : false"
  [usedCandidateRejectionTypeIds]="usedCandidateRejectionTypeIds"
  [usedCandidateStatusTypeIds]="usedCandidateStatusTypeIds"
  >
  </talent-new-edit-email-template>
</ng-template>
