<main class="careers {{ gridTemplateClass }}">
    <header class="careers__header">
        <div class="careers__header-logo">
            <img src={{clientInfo.logoUrl}} alt="Company Logo">
        </div>
    </header>
     
    <section class="careers__right-col">
        <div class="careers__toolbar" *ngIf="!details && !isToolbarCollapsed">
            <div class="careers__toolbar-top">
                <a href="#" class="e-link" *ngIf="details">View all jobs</a>
                <a class="e-link" target="_blank" href="{{clientInfo.webAddress}}">View our website</a>
                <button-base  [tooltip]="'Close the Filters'" [class]="['short flat']"
                [iconClass]="'fa-light fa-arrow-left'"
                (click)="toggleToolbar()"
                ></button-base>
            </div>
           
            <div class="careers__toolbar-form" [formGroup]="filtersForm">
                <input-text [form]="filtersForm" formControlName="searchFilter" [placeholder]="'Search'"
                    aria-label="Search"></input-text>
                <input-dropdown-multi [form]="filtersForm" formControlName="departmentFilter" [data]="departmentsList"
                    [enableFiltering]="true" mode="CheckBox" ngDefaultControl showSelectAll="true"
                    placeholder="Department">
                </input-dropdown-multi>
                <input-dropdown-multi [form]="filtersForm" formControlName="locationFilter" [data]="locationList"
                    [enableFiltering]="true" mode="CheckBox" ngDefaultControl showSelectAll="true"
                    placeholder="Location">
                </input-dropdown-multi>
                <div class="careers__toolbar-top">
                    <button-base [title]="'Clear'" [tooltip]="'Clear the filters'" [class]="['e-ghost']"
                        (click)="clearFilter()"></button-base>
                    <button-base [title]="'Apply'" [tooltip]="'Apply the filters'"
                        (click)="applyFilter()"></button-base>
                </div>

            </div>
        </div>

        <div class="careers__toolbar" *ngIf="isToolbarCollapsed">
            <div class="careers__toolbar-top">
              <a href="#" class="e-link" *ngIf="details">View all jobs</a>
                <a class="e-link" target="_blank" href="{{clientInfo.webAddress}}">View our website</a>
              <button-base
                [tooltip]="'Expand the Filters'"
                [class]="['short flat']"
                [iconClass]="'fa-light fa-arrow-right'"
                (click)="toggleToolbar()"
              ></button-base>
            </div>
          </div>


        <div class="careers__welcome" *ngIf="!details">
            <div class="careers__welcome-header">
                <h2>Welcome to the {{clientInfo.name}} Global Careers Page!</h2>
                <button-base [tooltip]="'Open full screen'" [class]="['short e-ghost']"
                    [iconClass]="'fa-regular fa-up-right-and-down-left-from-center'"
                    (click)="fullscrenmodal()"></button-base>
            </div>
            <div [innerHtml]="careerPortalHtml"></div> 
        </div>
         
      
        <div class="careers__job-details" *ngIf="details">
          <h3><strong class="custom-h3">Details</strong></h3>
          <div *ngIf="currentJobData?.closeDate" class="careers__job-details__department">
            <strong>Accepting Applications Until</strong>: {{ currentJobData?.closeDate | datetime:"DATETIME_FULL" }}
          </div>
          <div class="careers__job-details__department"
               *ngIf="currentJobData?.city && currentJobData?.state && currentJobData?.zipCode">
            <strong>Location</strong>: {{currentJobData?.city}},
            {{currentJobData?.state}} {{currentJobData?.zipCode}}
          </div>
          <div class="careers__job-details__department"
               *ngIf="currentJobData?.minPayRate && currentJobData?.maxPayRate && currentJobData?.paymentInterval && currentJobData?.showPayRate">
            <strong>Pay Rate</strong>:  {{currentJobData?.minPayRate}} -
            {{currentJobData?.maxPayRate}} {{currentJobData?.paymentInterval}}
          </div>
          <div class="careers__job-details__department"
               *ngIf="currentJobData?.department">
            <strong>Department</strong>:  {{currentJobData?.department}}
          </div>
          <div class="careers__job-details__department"
               *ngIf="currentJobData?.division">
            <strong>Division</strong>:  {{currentJobData?.division}}
          </div>
          <div class="careers__job-details__department"
               *ngIf="jobStatus">
            <strong>Job Status</strong>:  {{jobStatus}}
          </div>
          <div class="careers__job-details__department"
               *ngIf="currentJobData?.requisitionType">
            <strong>Position Type</strong>:  {{currentJobData?.requisitionType}}
          </div>
        </div>
    </section>
    <section class="careers__body" *ngIf="details">
      <div class="careers__body-controls margin-0 no-top-border">
        <a [routerLink]="['/careers']" routerLinkActive="active">
          <i class="fa-light fa-angle-left"></i>
          &nbsp;Back to Job
          Listings
        </a>

        <div class="careers__body-cta">
          <button-base [title]="'Apply '" (click)="scroll()"></button-base>
        </div>

      </div>
      <div class="careers__body-job-title">
        <h2>
          {{currentJobData?.title}}
        </h2>
        <div class="careers__body-job-location">
          <span class="careers__body-job-location__item" *ngIf="currentJobData?.department">{{currentJobData?.department}}</span>
          <span class="careers__body-job-location" *ngIf="currentJobData?.city && currentJobData?.state">{{currentJobData?.city}}, {{currentJobData?.state}}</span>
        </div>
      </div>

      <ng-container *ngIf="showDescription">
        <h3>Description</h3>
        <div class="careers__body-job-detail__wrapper">
          <div [innerHtml]="descriptionHtml"></div>
        </div>
      </ng-container>


      <ng-container *ngIf="showAdditionalInfo">
        <h3>Additional Information</h3>
        <div class="careers__body-job-detail__wrapper">
          <div [innerHtml]="additionalInformationHtml"></div>
        </div>
      </ng-container>

      
      <ng-container *ngIf="showDisclaimer">
        <h3>Disclaimer</h3>
        <div [innerHtml]="disclaimerHtml"></div>
      </ng-container>

    </section>

    <!-- All Jobs Listing  -->
    <section class="careers__body" *ngIf="!details">
        <div class="careers__body-header">
            <h1>Career Opportunities</h1>
            <!--<button-base 
              *ngIf="clientInfo.jobAlertsEnabled"
              [title]="'Job Alerts'"
              [tooltip]="'tooltip'"
              [class]="['e-ghost']"
              [iconClass]="'fa-solid fa-bell'" 
              aria-label="Job Alerts">
            </button-base>-->
        </div>
        <ul class="careers__body-rows">
            <li class="careers__body-rows__item" *ngFor="let data of allJobsList">

                <div class="careers__body-rows__item-title">
                    <a [routerLink]="['/careers',data.typeId]"
                        routerLinkActive="active">{{data.title}}</a>
                    <div class="careers__body-rows__item-title__detail">
                        <span *ngIf="data.department" >{{data.department}}</span> <span *ngIf="data.city">{{data.city}}, {{data.state}}</span>
                    </div>
                </div>
                <div class="careers__body-rows__item-cta">
                    <button-base [routerLink]="['/careers',data.typeId]"
                        [title]="'Apply '"></button-base>
                </div>
            </li>
        </ul>
    </section>

    <!-- Apply Form -->
    <section class="careers__body-form" *ngIf="details" #rightSection>
      <div class="careers__body-form__title">Apply for this position</div>
      <talent-application [requisitionTypeId]="currentJobId" [candidateSourceTypeId]="candidateSourceTypeId"></talent-application>
    </section>
</main>

<modal-base [config]="submitModal" [template]="editSetupContent"></modal-base>
<ng-template #editSetupContent>
    <div class="row">
        <div class="col-xs-12">
            <p>Thank you for applying to join our team. We have received your application for the <strong>PHP
                    Developer</strong> position. Our hiring team will review your submission and get back to you
                with
                the next steps. We appreciate your interest in our company and look forward to the possibility of
                working together.</p>
            <p><strong>What Happens Next?</strong> You can expect to hear from us within the next two weeks. If
                you're
                selected for the next round, we'll contact you to schedule an interview. In the meantime, feel free
                to
                check our website for updates or reach out if you have any questions.</p>
        </div>
    </div>
</ng-template>

<!-- fullscreen message -->
<modal-base [config]="fullscreenModal" [template]="fulllscreenmodalstuff"></modal-base>
<ng-template #fulllscreenmodalstuff>

    <div class="careers__welcome">
        <div [innerHtml]="careerPortalHtml"></div>
    </div>
</ng-template>
