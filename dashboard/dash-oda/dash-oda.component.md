<div class="dashboard__card">
    <dashboard-card-title [title]="'Overdue Appraisals'"></dashboard-card-title>
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
                <e-column field="EEDD" headerText="Employee Due Date"></e-column>
                <e-column field="ERDD" headerText="Employer Due Date"></e-column>
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
</div>