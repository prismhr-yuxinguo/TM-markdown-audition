<ejs-grid [allowPaging]="true" [dataSource]="posClass">
  <ng-template #toolbarTemplate let-data>
    <div class="custom-toolbar">
      <div class="custom-toolbar__wrapper">
        <div class="custom-toolbar__lc">
          <input-text
            [placeholder]="'Search'"
            [cssClass]="'search-bar'"
          ></input-text
          ><button-dropdown
            [items]="toolbarbtns"
            tooltip="Table tools"
            [callback]="select"
            [icon]="'prism-icons-toolbox'"
          ></button-dropdown>
        </div>
        <div class="custom-toolbar__rc">
          <button-base
            [title]="'New'"
            [callback]="callback"
            [tooltip]="'Add a new Resource'"
            (click)="newEmployee()"
          ></button-base>
        </div>
      </div>
    </div>
  </ng-template>

  <e-columns>
    <e-column field="ResourceName" headerText="Resource Name"></e-column>
    <e-column field="DateUploaded" headerText="Date Uploaded"></e-column>

    <e-column
      field=""
      textAlign="center"
      [template]="editbutton"
      width="80px"
    ></e-column>
  </e-columns>
</ejs-grid>
<ng-template #editbutton
  ><button-base
    [title]=""
    [tooltip]="'Delete'"
    [isPrimary]="false"
    [class]="['e-flat', 'advanced-search-btn']"
    [iconClass]="'fa-light fa-trash'"
    (click)="deleteBtn()"
  ></button-base>
  <!-- <button-dropdown-grid
    [items]="items"
    tooltip="Choose an option"
    [callback]="select"
  ></button-dropdown-grid> -->
</ng-template>

<ng-template #printBtn
  ><button-base
    [title]=""
    [tooltip]="'Print'"
    [isPrimary]="false"
    [class]="['e-flat', 'advanced-search-btn']"
    [iconClass]="'fa-light fa-print'"
    (click)="openAdvancedSearch()"
  ></button-base>
</ng-template>

<ng-template #pdfBtn
  ><button-base
    [title]=""
    [tooltip]="'Download as PDF'"
    [isPrimary]="false"
    [class]="['e-flat', 'advanced-search-btn']"
    [iconClass]="'fa-light fa-file-pdf'"
    (click)="openAdvancedSearch()"
  ></button-base>
</ng-template>

<ng-template #csvBtn
  ><button-base
    [title]=""
    [tooltip]="'Download as CSV'"
    [isPrimary]="false"
    [class]="['e-flat', 'advanced-search-btn']"
    [iconClass]="'fa-light fa-file'"
    (click)="openAdvancedSearch()"
  ></button-base>
</ng-template>

<ng-template #excelBtn
  ><button-base
    [title]=""
    [tooltip]="'Download as Excel'"
    [isPrimary]="false"
    [class]="['e-flat', 'advanced-search-btn']"
    [iconClass]="'fa-light fa-file-excel'"
    (click)="openAdvancedSearch()"
  ></button-base>
</ng-template>

<ng-template #copyBtn
  ><button-base
    [title]=""
    [tooltip]="'Copy'"
    [isPrimary]="false"
    [class]="['e-flat', 'advanced-search-btn']"
    [iconClass]="'fa-light fa-copy'"
    (click)="openAdvancedSearch()"
  ></button-base>
</ng-template>

<ng-template #advancedSearchBtn
  ><button-base
    [title]=""
    [tooltip]="'Toggle Search Filters'"
    [isPrimary]="false"
    [class]="['e-flat', 'advanced-search-btn']"
    [iconClass]="'fa-light fa-cog'"
    (click)="openAdvancedSearch()"
  ></button-base
></ng-template>
<ng-template #searchbar>
  <input-text
    [placeholder]="'Search'"
    [cssClass]="'search-bar'"
  ></input-text
></ng-template>
<!-- delete -->
<modal-base [config]="deleteModal" [template]="deleteContent"></modal-base>
<ng-template #deleteContent>
  <div class="row">
    <div class="col-xs-12">
      Are you sure you want to delete this resource? Once deleted, it cannot be
      recovered.
    </div>
  </div>
</ng-template>

<!-- new -->
<modal-base [config]="newTypeModal" [template]="newTypeContent"></modal-base>
<ng-template #newTypeContent>
  <settings-table>
    <settings-row [title]="'New Resource'" [description]="">
      <settings-uploader></settings-uploader>
    </settings-row>
  </settings-table>
</ng-template>

<!-- delete -->
<modal-base
  [config]="editSetupModal"
  [template]="editSetupContent"
></modal-base>
<ng-template #editSetupContent>
  <settings-table>
    <settings-row [title]="'New Resource'" [description]="">
      <settings-uploader></settings-uploader>
    </settings-row>
  </settings-table>
</ng-template>
