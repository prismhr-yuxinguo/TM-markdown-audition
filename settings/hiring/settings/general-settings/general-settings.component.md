<talent-footer
  [nextVisible]="false"
  [prevVisible]="false"
  (saveClicked)="save()"
  [saveEnabled]="saveEnabled"
  [saveVisible]="isEditable"
>
</talent-footer>

<fieldset [formGroup]="hiringSettingForm" [disabled]="!isEditable">
  <settings-table>
    <settings-row
      [title]="'Collect SSN On Hire?'"
      [description]="
        'Toggle On/Off the ability for admins and hiring managers to manually enter a new hire\'s Social Security Number on the Hire detail screen.'
      "
      [required]=""
    >
      <toggle-switch
        [form]="hiringSettingForm"
        formControlName="collectSSNOnHire"
        [enabled]="isEditable"
      ></toggle-switch>
    </settings-row>

    <settings-row
      [title]="'Collect Date of Birth On Hire?'"
      [description]="
        'Toggle On/Off the ability for admins and hiring managers to manually enter a new hire\'s Date of Birth on the Hire Detail screen.'
      "
      [required]=""
    >
      <toggle-switch
        [form]="hiringSettingForm"
        formControlName="collectDOBOnHire"
        [enabled]="isEditable"
      ></toggle-switch>
    </settings-row>

    <settings-row [title]="'Collect SSN On Offer Letter?'" [description]="" [required]="">
      <toggle-switch
        [form]="hiringSettingForm"
        formControlName="collectSSNOnOfferLetter"
        [enabled]="isEditable"
      ></toggle-switch>
    </settings-row>

    <settings-row [title]="'Collect Date of Birth On Offer Letter?'" [description]="" [required]="">
      <toggle-switch
        [form]="hiringSettingForm"
        formControlName="collectDOBOnOfferLetter"
        [enabled]="isEditable"
      ></toggle-switch>
    </settings-row>

    <!-- <settings-row
      [title]="'Allow Internal Candidates to Apply?'"
      [description]="
        'Allow current employees to submit job applications from the Employee Dashboard.'
      "
      [required]=""
    >
      <toggle-switch
        [form]="hiringSettingForm"
        formControlName="allowInternalCandidate"
      ></toggle-switch>
    </settings-row> -->

    <!-- <settings-row
      [title]="'Utilize Basic Minimum Qualifications?'"
      [description]="'Allow assessments to define BMQ questions.'"
      [required]=""
    >
      <toggle-switch
        [form]="hiringSettingForm"
        formControlName="allowBasicMinimumQualification"
      ></toggle-switch>
    </settings-row> -->

    <!-- <settings-row
      [title]="'Allow Hiring Manager Rating?'"
      [description]="
        'Allow hiring manager to provide a candidate rating when candidates are routed to them.'
      "
      [required]=""
    >
      <toggle-switch
        [form]="hiringSettingForm"
        formControlName="allowHiringManagerRating"
      ></toggle-switch>
    </settings-row> -->

    <!-- <settings-row
      [title]="'Allow Automated Candidate Routing?'"
      [description]="
        'Allow system to automatically route candidates based on position workflow.'
      "
      [required]=""
    >
      <toggle-switch
        [form]="hiringSettingForm"
        formControlName="allowAutomatedCandidateRouting"
      ></toggle-switch>
    </settings-row>

    <settings-row
      [title]="'Position Description Feedback Available?'"
      [description]="
        'Turn on/off position description feedback routing functionality.'
      "
      [required]=""
    >
      <toggle-switch
        [form]="hiringSettingForm"
        formControlName="jobDescriptionApproval"
      ></toggle-switch>
    </settings-row>

    <settings-row
      [title]="'Include Credit Report Statement?'"
      [description]=""
      [required]=""
    >
      <toggle-switch
        [form]="hiringSettingForm"
        formControlName="allowCreditReport"
      ></toggle-switch>
    </settings-row>

    <settings-row
      [title]="
        'Include \'I would like to obtain a copy of the credit report\' option?'
      "
      [description]=""
      [required]=""
    >
      <toggle-switch
        [form]="hiringSettingForm"
        formControlName="allowCopyOfCreditReport"
      ></toggle-switch>
    </settings-row> -->

    <settings-row
      [title]="'Require Salary Range for Postings '"
      [description]="'Checking this box will make salary range a required field when posting a requisition.'"
      [required]=""
    >
      <toggle-switch
        [form]="hiringSettingForm"
        formControlName="requireSalaryRangeForPostings"
        [enabled]="isEditable && !isIndeedEnabled"
      ></toggle-switch>
    </settings-row>

    <settings-row [title]="'Employment Page URL'" [description]="" [required]="">
      <input-text
        [placeholder]="'Employment Page URL'"
        [form]="hiringSettingForm"
        formControlName="employmentPageUrl"
      ></input-text>
    </settings-row>
  </settings-table>
</fieldset>
