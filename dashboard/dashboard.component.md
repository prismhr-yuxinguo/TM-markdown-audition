<page-title [title]="'Relaxation Destinations Dashboard'"></page-title>
<!-- <illustration-block
  [illustrationBlockTitle]="'Time again'"
  [illustrationBlockDescription]="'asdasd'"
></illustration-block> -->
<div class="dashboard">
  <div class="dashboard__top">
    <quicklinks [links]='quicklinks'></quicklinks>

    <div class="dashboard__top-layout">
      <ejs-tooltip #tooltip content="Reset Dashboard layout">
        <button class="dashboard__layout-resize"
                tabindex="0"
                aria-label="Reset Dashboard layout"
                #restoreBtn
                (click)="onrestoreClick($event)">
          <div class="dashboard__design" aria-hidden="true">
            <div class="dashboard__design-a"></div>
            <div class="dashboard__design-b"></div>
            <div class="dashboard__design-c"></div>
            <div class="dashboard__design-d"></div>
          </div>
        </button>
      </ejs-tooltip>
    </div>
  </div>
  <ejs-dashboardlayout #defaultLayout
                       columns="12"
                       [cellSpacing]="[24, 24]"
                       [allowResizing]="true"
                       (resizeStop)="onResizeStop($this)"
                       (resizeStart)="onResizeStart($this)"
                       (resize)="onResize($this)"
                       (dragStart)="onDragStart($this)"
                       (drag)="onDrag($this)"
                       (dragStop)="onDragStop($this)"
                       [showGridLines]="showGridLines"
                       [panels]="panels"
                       [mediaQuery]='mediaQuery'>
    <ng-template #dash1>
      <div class="dashboard-mini">
        <img draggable="false"
             class="dashboard-mini__image"
             src="{{ imagePath }}" />
        <div class="dashboard-mini__figure">15</div>
        <div class="dashboard-mini__title">Active Appraisals</div>
        <div class="dashboard-mini__cta">
          <ejs-tooltip #tooltip content="View all ">
            <a href="#"><i class="fa-light fa-angle-right"></i></a>
          </ejs-tooltip>
        </div>
      </div>
    </ng-template>

    <ng-template #dash2>
      <div class="dashboard-mini">
        <img draggable="false"
             class="dashboard-mini__image"
             src="{{ imagePath2 }}" />
        <div class="dashboard-mini__figure">30</div>
        <div class="dashboard-mini__title">Appraisals Ready</div>
        <div class="dashboard-mini__cta">
          <ejs-tooltip #tooltip content="View all Appraisals Ready">
            <a href="#"><i class="fa-light fa-angle-right"></i></a>
          </ejs-tooltip>
        </div>
      </div>
    </ng-template>

    <ng-template #dash3>
      <div class="dashboard-mini">
        <img draggable="false"
             class="dashboard-mini__image"
             src="{{ imagePath3 }}" />
        <div class="dashboard-mini__figure">0</div>
        <div class="dashboard-mini__title">Overdue Appraisals</div>
        <div class="dashboard-mini__cta">
          <ejs-tooltip #tooltip content="View all >Overdue Appraisals">
            <a href="#"><i class="fa-light fa-angle-right"></i></a>
          </ejs-tooltip>
        </div>
      </div>
    </ng-template>

    <ng-template #dash4>
      <div class="dashboard-mini">
        <img draggable="false"
             class="dashboard-mini__image"
             src="{{ imagePath4 }}" />
        <div class="dashboard-mini__figure">0</div>
        <div class="dashboard-mini__title">Outstanding Milestones</div>
        <div class="dashboard-mini__cta">
          <ejs-tooltip #tooltip content="View all Outstanding Milestones">
            <a href="#"><i class="fa-light fa-angle-right"></i></a>
          </ejs-tooltip>
        </div>
      </div>
    </ng-template>

    <ng-template #dash5>
      <app-dash-spline></app-dash-spline>
    </ng-template>

    <ng-template #dash6>
      <app-dash-oda></app-dash-oda>
    </ng-template>

    <ng-template #dash7>
      <app-dash-appr></app-dash-appr>
    </ng-template>

    <ng-template #dash8>
      <app-dash-om></app-dash-om>
    </ng-template>

    <ng-template #dash9>
      <app-dash-ac></app-dash-ac>
    </ng-template>

    <ng-template #dash10>
      <app-dash-cws></app-dash-cws>
    </ng-template>
    <ng-template #dash11>
      <div class="dashboard-mini dashboard-mini--center">
        <div class="dashboard-mini__figure">{{candidateRequisitionCounts?.candidatesToday || 0}}</div>
        <div class="dashboard-mini__title">Candidates Today</div>
      </div>
    </ng-template>

    <ng-template #dash12>
      <div class="dashboard-mini dashboard-mini--center">
        <div class="dashboard-mini__figure">{{candidateRequisitionCounts?.candidatesThisMonth || 0}}</div>
        <div class="dashboard-mini__title">{{currentMonth}}  Candidates</div>
      </div>
    </ng-template>

    <ng-template #dash13>
      <div class="dashboard-mini dashboard-mini--center">
        <div class="dashboard-mini__figure">{{candidateRequisitionCounts?.candidatesThisYear || 0}}</div>
        <div class="dashboard-mini__title">{{currentYear}} Candidates</div>
      </div>
    </ng-template>

    <ng-template #dash14>
      <div class="dashboard-mini dashboard-mini--center">
        <div class="dashboard-mini__figure">{{candidateRequisitionCounts?.candidatesAllTime || 0}}</div>
        <div class="dashboard-mini__title">All-Time Candidates</div>
      </div>
    </ng-template>

    <ng-template #dash15>
      <div class="dashboard-mini dashboard-mini--center">
        <div class="dashboard-mini__figure">{{candidateRequisitionCounts?.requisitionsActive || 0}}</div>
        <div class="dashboard-mini__title">Active Requisitions</div>
      </div>
    </ng-template>

    <ng-template #dash16>
      <div class="dashboard-mini dashboard-mini--center">
        <div class="dashboard-mini__figure">{{candidateRequisitionCounts?.requisitionsPublished || 0}}</div>
        <a href="/hiring/requisitions#statusesFilter=Published">
          <div class="dashboard-mini__title">Published Requisitions</div>
        </a>
      </div>
    </ng-template>

    <ng-template #dash17>
      <div class="dashboard-mini dashboard-mini--center">
        <div class="dashboard-mini__figure">{{candidateRequisitionCounts?.requisitionsInProgress || 0}}</div>
        <a href="/hiring/requisitions#statusesFilter=In+Progress">
          <div class="dashboard-mini__title">In Progress Requisitions</div>
        </a>
      </div>
    </ng-template>

    <ng-template #dash18>
      <div class="dashboard-mini dashboard-mini--center">
        <div class="dashboard-mini__figure">{{candidateRequisitionCounts?.requisitionsFilledThisYear || 0}}</div>
        <div class="dashboard-mini__title">{{currentYear}} Filled Requisitions</div>
      </div>
    </ng-template>

    <ng-template #dash19>
      <app-dash-cpv></app-dash-cpv>
    </ng-template>
  </ejs-dashboardlayout>
</div>
