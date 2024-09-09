<page-title [title]="'Employee Dashboard Message'"></page-title>
<talent-footer [nextVisible]="false"
               [prevVisible]="false"
               (saveClicked)="save()"
               [saveEnabled]="saveEnabled"
               [saveVisible]="hasEdit"></talent-footer>
<settings-table>
  <settings-row [title]="'Message'"
                [description]=""
                [required]=""
                [type]="'WYSIWYG'">
    <input-rich-text id="defaultRTE"
                     [toolbarSettings]="editorTools"
                     [form]="employeeDashboardMessageForm"
                     formControlName="selfServiceInstructions"></input-rich-text>
  </settings-row>
</settings-table>
