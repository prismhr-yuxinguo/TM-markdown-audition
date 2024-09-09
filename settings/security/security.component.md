<page-title [title]="'Roles'"></page-title>

<talent-grid
  #grid
  [allowBulkActions]="false"
  [allowFiltering]="false"
  [allowNew]="hasCreate"
  [allowRowSelect]="false"
  [data]="roles"
  exportFileName="Roles"
  friendlyName="Role"
  idProperty="typeId"
  [initializing]="initializing"
  [searchFields]="['name', 'description']"
  (selected)="selected($event)"
  [selectOptions]="selectOptions"
>
  <e-columns>
    <e-column field="isBuiltIn" headerText="" width="40">
      <ng-template #template let-data>
        @if (data.isBuiltIn) {
        <ejs-tooltip #tooltip content="Built-In Role">
          <span class="fa-xl prism-icons-prism"></span>
        </ejs-tooltip>
        }
      </ng-template>
    </e-column>
    <e-column field="name" headerText="Name">
      <ng-template *hasKey="[Keys.CoreRolesEdit, Keys.CoreRolesView]" #template let-data>
        <ejs-tooltip #tooltip
                     [content]="editOrViewTooltip">
          <a class="grid-link disable-row-select" (click)="onLinkClicked($event, data)">{{ data.name }}</a>
        </ejs-tooltip>
      </ng-template>
    </e-column>
    <e-column field="description" headerText="Description"></e-column>
  </e-columns>
</talent-grid>

<!-- delete -->
<modal-base [config]="deleteModal" [template]="deleteContent"></modal-base>
<ng-template #deleteContent>
  <div class="row">
    <div class="col-xs-12">
      Are you sure you want to delete this role? Once deleted, it cannot be
      recovered.
    </div>
  </div>
</ng-template>

<!-- copy -->
<modal-base [config]="copyModal" [template]="copyContent"></modal-base>
<ng-template #copyContent>
  <div class="row">
    <div class="col-xs-12">Are you sure you want to copy this item?</div>
  </div>
</ng-template>

<!-- new/edit -->
<modal-base
  [config]="editSetupModal"
  [template]="editSetupContent"
></modal-base>
<ng-template #editSetupContent>
  <settings-table>
    <settings-row [title]="' Name'" [description]="" [required]="true">
      <input-text
        [placeholder]="' Name'"
        [required]="true"
        [enabled]="togglesEnabled"
        [form]="roleModalFormGroup"
        formControlName="name"
      ></input-text>
    </settings-row>
    <settings-row [title]="' Description'" [description]="" [required]="true">
      <input-text
        [placeholder]="' Description'"
        [required]="true"
        [enabled]="togglesEnabled"
        [form]="roleModalFormGroup"
        formControlName="description"
      ></input-text>
    </settings-row>
  </settings-table>
  @for (module of keysDefinition | keyvalue: sortNone; track module.key) {
  <settings-table
    [settingsTitle]="module.value.name"
    *hasModule="module.value.modules"
  >
    @for (type of module.value.items | keyvalue: sortNone; track type.key) {
    <ng-container *hasModule="type.value.modules || []">
      @if (type.value.name !== module.value.name) {
      <settings-row [subtitle]="type.value.name"></settings-row>
      } @for (key of type.value.items | keyvalue: sortNone; track key.key) { @if
      (key.value.visible) {
      <settings-row
        [title]="key.value.name"
        [description]="key.value.description"
      >
        <toggle-switch
          (check)="key.value.check?.($event)"
          [enabled]="togglesEnabled"
          [formControl]="key.value.checked"
        ></toggle-switch>
      </settings-row>
      } }
    </ng-container>
    }
  </settings-table>
  }
</ng-template>
