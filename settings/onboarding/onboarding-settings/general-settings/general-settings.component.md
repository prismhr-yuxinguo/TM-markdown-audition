<talent-footer
  [nextVisible]="false"
  [prevVisible]="false"
  (saveClicked)="save()"
  [saveEnabled]="saveEnabled"
  [saveVisible]="isEditable"
>
</talent-footer>

<ng-container [formGroup]="onboardingSettingForm">
  <settings-table>
    <!-- <settings-row
      [title]="'Automated Plan Creation'"
      [description]="
        'The ability to automatically create plans when employees are added to the system.'
      "
      [required]=""
      [maxLines]="2"
    >
      <toggle-switch
        [form]="onboardingSettingForm"
        formControlName="automatedPlanCreation"
      ></toggle-switch>
    </settings-row> -->
    <settings-row [title]="'Require SSN on Personal Information'"
                  [description]="
        'Turn on/off the requirement of the new hire\'s Social Security Number (SSN) on the Personal Information screen.'
      "
                  [required]=""
                  [maxLines]="2">
      <toggle-switch [form]="onboardingSettingForm"
                     formControlName="socialSecurityRequired"
                     [enabled]="isEditable"></toggle-switch>
    </settings-row>

    <!-- <settings-row
      [title]="'Tax Forms Flow'"
      [description]="
        'Control how tax forms are presented to employees. Guided is based on the employee\'s home and work addresses, whereas Choose allows administrators to define which individual tax forms will be included in each template.'
      "
      [required]=""
    >
      <input-dropdown
        [data]="showTaxFormItems"
        [form]="onboardingSettingForm"
        formControlName="taxFormsFlow"
        ngDefaultControl
        placeholder="Tax Form Flow"
      >
      </input-dropdown>
    </settings-row> -->
    <!-- <settings-row
      [title]="'Show Employee Onboarding History'"
      [description]="
        'Allow employees to see all their onboarding plan history. If off, they will only see plans that have been launched.'
      "
      [required]=""
    >
      <toggle-switch
        [form]="onboardingSettingForm"
        formControlName="showEmployeeOnboardingHistory"
      ></toggle-switch>
    </settings-row> -->
  </settings-table>
</ng-container>
