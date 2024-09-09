<page-title [title]="'Billing Information'"></page-title>
<talent-footer (customButtonClicked)="toggleModal(true)"
               [customButtons]="customButtons"
               [nextVisible]="false"
               [prevVisible]="false"
               (saveClicked)="save()"
               [saveEnabled]="true"
               [saveVisible]="true"></talent-footer>

<ejs-tab id="element">
  <e-tabitems>
    <e-tabitem>
      <ng-template #headerText>
        <div>
          User Billing Information
        </div>
      </ng-template>
      <ng-template #content>
        <ng-container [formGroup]="billInfoForm">
          <settings-table>
            <settings-row [title]="'Account Email'" [required]="true">
              <input-text [placeholder]="" [form]="billInfoForm" formControlName="email"></input-text>
            </settings-row>
            <settings-row [title]="'Name on Card'" [required]="true">
              <input-text [placeholder]="" [form]="billInfoForm" formControlName="name"></input-text>
            </settings-row>
            <settings-row [title]="'Card Number'" [description]="" [required]="isNew" *ngIf="!isNew">
              <input-text [placeholder]="" [form]="billInfoForm" formControlName="cardNumber" [enabled]="isNew"></input-text>
            </settings-row>
            <settings-row [title]="'Card Number'" [description]="" [required]="isNew" *ngIf="isNew">
              <ejs-maskedtextbox form="billInfoForm" formControlName="cardNumber" mask="0000 0000 0000 0000" placeholder="Card Number" floatLabelType="Auto" required="isNew"></ejs-maskedtextbox>
              <p *ngIf="billInfoForm.controls.cardNumber.invalid && billInfoForm.controls.cardNumber.touched" class="error-message masked-value-error-message">
                This field is required
              </p>
            </settings-row>
            <settings-row [title]="'Expiration Month'" [required]="true">
              <input-text [placeholder]="" [required]="true" [form]="billInfoForm" formControlName="expMonth"></input-text>
            </settings-row>
            <settings-row [title]="'Expiration Year'" [required]="true">
              <input-text [placeholder]="" [required]="true" [form]="billInfoForm" formControlName="expYear"></input-text>
              <p *ngIf="expirationDateErrors() | async" class="error-message custom-error-message"> {{ expirationDateErrors() | async }}</p>
            </settings-row>
            <settings-row [title]="'CVC'" [required]="isNew" *ngIf="!isNew">
              <input-text [placeholder]="" [form]="billInfoForm" formControlName="cvc" [enabled]="isNew"></input-text>
            </settings-row>
            <settings-row [title]="'CVC'" [description]="" [required]="isNew" *ngIf="isNew">
              <ejs-maskedtextbox form="billInfoForm" formControlName="cvc" mask="0000" placeholder="Card Number" floatLabelType="Auto" required="isNew"></ejs-maskedtextbox>
              <p *ngIf="billInfoForm.controls.cvc.invalid && billInfoForm.controls.cvc.touched" class="error-message masked-value-error-message">
                This field is required
              </p>
            </settings-row>

            <settings-row [title]="'Billing Address 1'" [required]="true">
              <input-text [placeholder]="" [form]="billInfoForm" formControlName="addressLine1"></input-text>
            </settings-row>
            <settings-row [title]="'Billing Address 2'">
              <input-text [placeholder]="" [form]="billInfoForm" formControlName="addressLine2"></input-text>
            </settings-row>
            <settings-row [title]="'Billing City'" [required]="true">
              <input-text [placeholder]="" [form]="billInfoForm" formControlName="city"></input-text>
            </settings-row>
            <settings-row [title]="'Billing State'" [description]="" [required]="true">
              <input-dropdown [data]="states"
                              [form]="billInfoForm" formControlName="state"
                              [placeholder]="'State'"
                              [enableFiltering]="true"
                              [filtering]="true"
                              [required]="true"></input-dropdown>
            </settings-row>
            <settings-row [title]="'Billing Zip'" [required]="true">
              <ejs-maskedtextbox form="billInfoForm" formControlName="postalCode" mask="000000000" placeholder="" floatLabelType="Auto" required="isNew"></ejs-maskedtextbox>
              <p *ngIf="billInfoForm.controls.postalCode.invalid && billInfoForm.controls.postalCode.touched" class="error-message masked-value-error-message">
                This field is required
              </p>
            </settings-row>
          </settings-table>
        </ng-container>
      </ng-template>
    </e-tabitem>

    <e-tabitem>
      <ng-template #headerText>
        <div>
          Transaction History
        </div>
      </ng-template>
      <ng-template #content>
        <talent-grid #grid
                     [allowBulkActions]="false"
                     [allowFiltering]="false"
                     [allowNew]="false"
                     [allowRowSelect]="false"
                     [data]="invoiceDetails"
                     exportFileName="Transaction History"
                     friendlyName="InvoiceDetails"
                     [searchFields]="searchFields"
                     [selectActionTooltip]="selectActionTooltip"
                     [selectOptions]="selectOptions"
                     (selected)="selected($event)"
                     (sortDir)="sortDirChanged($event)">
          <e-columns>
            <e-column field="number" headerText="Invoice #" maxWidth="150" [sortComparer]="emptySortComparer"></e-column>
            <e-column field="created" headerText="Invoice Date" [sortComparer]="emptySortComparer"></e-column>
            <e-column field="description" headerText="Description" [sortComparer]="emptySortComparer"></e-column>
            <e-column field="amount" headerText="Amount" [sortComparer]="emptySortComparer" format='C2'></e-column>
          </e-columns>
        </talent-grid>
      </ng-template>
    </e-tabitem>
  </e-tabitems>
</ejs-tab>

<!-- #confirmation -->
<modal-base [config]="confirmationPopupConfig" [template]="confirmationContent"></modal-base>
<ng-template #confirmationContent>
  <div class="row">
    <div class="col-xs-12">
      {{ confirmationMessage}}
    </div>
  </div>
</ng-template>


