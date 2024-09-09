<message-panel [title]="'Attention'"
               [content]="'Check each section you wish to include in your application (some are required and cannot be unchecked). You can also drag and drop to reorder the sections in the order you want them presented.'"
               [state]="0"></message-panel>

<div class="definition-container">
  <fieldset [disabled]="!isEditable">
    <ejs-listbox [dataSource]="data" [allowDragAndDrop]="isEditable" (drop)='onDropData($event)'>
      <ng-template #itemTemplate let-data>
        <div class="definition-wrapper">
          <ejs-checkbox class="definition-checkbox" [id]="data.id" [(ngModel)]="data.isSelected" [disabled]="data.isLocked || !isEditable" (change)="onCheckBoxChange($event)"></ejs-checkbox> <span class="settings__title definition-name" [ngClass]="{'required': data.isLocked}" [innerText]="data.text"></span>
          <p class="definition-description">
            <span [innerHTML]="data.description"></span>
          </p>
        </div>
      </ng-template>
    </ejs-listbox>
  </fieldset>
</div>
