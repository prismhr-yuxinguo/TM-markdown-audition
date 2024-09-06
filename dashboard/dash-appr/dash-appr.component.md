<div class="dashboard__card">
    <dashboard-card-title [title]="'Current Appraisals'">
        <div class="advanced-search">
            <button-base [title]=""
                         [tooltip]="'Toggle Search Filters'"
                         [isPrimary]="false"
                         [class]="['e-flat', 'advanced-search-btn']"
                         [iconClass]="'fa-light fa-filter-list'"
                         (click)="openAdvancedSearch()"></button-base>
            <input-text [placeholder]="'Search'" [cssClass]="'search-bar'"></input-text>
        </div>
    </dashboard-card-title>
    <dashboard-card-body>
        <ejs-grid [allowPaging]="true"
                  [dataSource]="griddata"
                  allowSorting="true"
                  allowPaging="true"
                  [loadingIndicator]="loadingIndicator"
                  [enableAdaptiveUI]="true"
                  height="100%">
            <e-columns>
                <e-column field="Employee" headerText="Employee"></e-column>
                <e-column field="Supervisor" headerText="Supervisor"></e-column>
                <e-column field="From" headerText="From" width="120px"></e-column>
                <e-column field="To" headerText="To" width="120px"></e-column>
                <e-column field="Status"
                          headerText=""
                          [template]="statusTemplate"
                          width="50px"></e-column>
                <e-column field=""
                          textAlign="center"
                          [template]="editbutton"
                          width="80px"></e-column>
            </e-columns>
        </ejs-grid>
    </dashboard-card-body>
    <!-- dropdwon nav -->
    <ng-template #editbutton>
        <button-dropdown-grid [items]="items"
                              tooltip="Choose an option"
                              [callback]="select"></button-dropdown-grid>
    </ng-template>
    <!-- evaluate status -->
    <ng-template #statusTemplate let-data>
        <div [ngClass]="'status__' + removeWhiteSpace(data.Status)">
            <ejs-tooltip #tooltip content="Status: {{ data.Status }}">
                {{ shorten(data.Status) }}
            </ejs-tooltip>
        </div>
    </ng-template>
    <!--  -->
    <!-- delete -->
    <modal-base [config]="appraiseEmployeeModal"
                [template]="appraiseEmployee"></modal-base>
    <ng-template #appraiseEmployee>
        <div class="row">
            <div class="col-xs-12">
                Are you sure you want to delete this job cost? Once deleted, it cannot be
                recovered.
            </div>
        </div>
    </ng-template>

    <!-- delete -->
    <modal-base [config]="advancedSearchModal"
                [template]="editSetupContent"></modal-base>
    <ng-template #editSetupContent>
        <settings-table>
            <settings-row [title]="" [description]="" [required]=""> </settings-row>
        </settings-table>
    </ng-template>
</div>