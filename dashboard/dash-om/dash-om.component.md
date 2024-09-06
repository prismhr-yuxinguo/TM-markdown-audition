<div class="dashboard__card">
    <dashboard-card-title [title]="'Outstanding Feedback Milestones'">
        <button-base [title]=""
                     [tooltip]="'Peer Feedback'"
                     [isPrimary]="false"
                     [iconClass]="'fa-light fa-messages'"
                     [class]="['e-short e-ghost']"
                     (onClick)="openPeerFeedbackModal()"></button-base>
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
                <e-column field="Date" headerText="Date" width="120px"></e-column>
                <e-column width="80px" [template]="editbutton"></e-column>
            </e-columns>
        </ejs-grid>
    </dashboard-card-body>
    <!-- dropdwon nav -->
    <ng-template #editbutton>
        <button-base [tooltip]="'Edit this milestone'"
                     [class]="['flat ']"
                     [iconClass]="'fa-light fa-pen'"
                     (click)="editTheModal()"></button-base>
    </ng-template>
    <!-- delete -->
    <modal-base [config]="editModal" [template]="editSetupContent"></modal-base>
    <ng-template #editSetupContent>
        <settings-table>
            <settings-row [title]="'Employee'" [description]="" [required]="">
                <input-text [placeholder]="'Employee'"
                            [value]="'Andrew Harris'"
                            [enabled]="false"></input-text>
            </settings-row>
            <settings-row [title]="'Supervisor'" [description]="" [required]="">
                <input-text [placeholder]="'Supervisor'"
                            [value]="'Andrew Harris'"
                            [enabled]="false"></input-text>
            </settings-row>
            <settings-row [title]="'Milestone Date'" [description]="" [required]="true">
                <input-datepicker [placeholder]="'Milestone Date'"
                                  [required]="true"></input-datepicker>
            </settings-row>
            <settings-row [title]="'Is Milestone Complete?'" [description]="">
                <toggle-switch></toggle-switch>
            </settings-row>
        </settings-table>
    </ng-template>
    <!-- perf feedback -->
    <modal-base [config]="peerFeedbackModal"
                [template]="peerFeedbackSetupContent"></modal-base>
    <ng-template #peerFeedbackSetupContent>
        <settings-table>
            <settings-row [title]="'Employee'" [description]="" [required]="true">
                <input-dropdown [data]="data"
                                [value]="value"
                                [placeholder]="'Employee'"
                                [enableFiltering]="true"
                                [filtering]="true"
                                [required]="true"></input-dropdown>
            </settings-row>
            <settings-row [title]="'Supervisor'" [description]="" [required]="">
                <input-dropdown [data]="data"
                                [value]="value"
                                [placeholder]="'Employee'"
                                [enableFiltering]="true"
                                [filtering]="true"
                                [required]="true"></input-dropdown>
            </settings-row>
            <settings-row [title]="'Milestone Date'" [description]="" [required]="true">
                <input-datepicker [placeholder]="'Milestone Date'"
                                  [required]="true"></input-datepicker>
            </settings-row>
            <settings-row [title]="'Send Feedback Confidentially?'"
                          [description]="
        'When this box is checked neither the employee nor supervisor will be able to see your identity; however, System Administrators will be able to see your identity.'
      ">
                <toggle-switch></toggle-switch>
            </settings-row>
            <settings-row [title]="'Provide Feedback about Employee'" [type]="'WYSIWYG'">
                <ejs-richtexteditor></ejs-richtexteditor>
            </settings-row>
        </settings-table>
    </ng-template>
</div>