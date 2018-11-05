---
title: Grid �s�̕ҏW - �l�C�e�B�u Angular | Ignite UI for Angular
_description: �s�ҏW - �O���b�h �f�[�^�\�[�X�ɕύX���T�u�~�b�g����O�ɍs�̕����Z������x�ɕύX���邱�Ƃ��\�ł��B�V�����g�����U�N�V���� �v���o�C�_�[�ۗ̕����̕ύX�𗘗p�ł��܂��B
_keywords: Ignite UI for Angular, UI controls, Angular widgets, web widgets, UI widgets, Angular, Native Angular Components Suite, Native Angular Controls, Native Angular Components Library, Native Angular Component, Angular Grid, Angular Data Grid component, Angular Data Grid control, Angular Grid component, Angular Grid control, Angular High Performance Grid, Cell Editing
_language: ja
---

## �O���b�h�ҏW

�s�ҏW - �O���b�h �f�[�^�\�[�X�ɕύX���T�u�~�b�g����O�ɍs�̕����Z������x�ɕύX���邱�Ƃ��\�ł��B�V�����g�����U�N�V���� �v���o�C�_�[�ۗ̕����̕ύX�𗘗p�ł��܂��B



### �f��

�ȉ��̎菇�ł́A�O���b�h�ōs�ҏW��L���ɂ�����@�������܂��B�Z���l��ύX���Ă��瓯���s�̑��̃Z�����N���b�N�܂��̓i�r�Q�[�V���������ꍇ�� Done �{�^�����g�p���Ċm�肷��܂ōs�l���X�V���܂���B�܂��� Cancel �{�^�����g�p���Ĕj�����܂��B

<div class="sample-container loading" style="height:650px">
    <iframe id="grid-row-editing-sample-iframe" src='{environment:demosBaseUrl}/grid-row-editing' width="100%" height="100%" seamless frameBorder="0" onload="onSampleIframeContentLoaded(this);"></iframe>
</div>
<br/>
<div>
<button data-localize="stackblitz" disabled class="stackblitz-btn" data-iframe-id="grid-row-editing-sample-iframe" data-demos-base-url="{environment:demosBaseUrl}">view on stackblitz</button>
</div>

> [!NOTE]
> �s���ҏW���[�h�ɂ���ꍇ�A���̍s�̃Z�����N���b�N����� Done �{�^���������ꂽ�悤�ɓ��삵�A�O�̍s�̕ύX�����ׂĂ̕ύX���T�u�~�b�g���܂��B�t�H�[�J�X�̂���V�����Z�����ҏW�\���ǂ����A�V�����s���ҏW���[�h�ɓ��邩�ǂ����A�Z�����ҏW�ł��Ȃ��ꍇ�͑O�̍s�̂ݕҏW���[�h���I�����܂��B

<div class="divider--half"></div>

## �g�p���@

[IgxGridModule]({environment:angularApiUrl}/classes/igxgridmodule.html) in the **app.module.ts** �t�@�C�����C���|�[�g���܂��B

```typescript
// app.module.ts

...
import { IgxGridModule } from 'igniteui-angular';

@NgModule({
    ...
    imports: [..., IgxGridModule],
    ...
})
export class AppModule {}
```

�f�[�^�\�[�X�Ƀo�C���h����O���b�h���`������ [`rowEditable`]({environment:angularApiUrl}/classes/igxgridcomponent.html#roweditable) �� true �ɐݒ肵�܂��B

```html
<div class="sample-wrapper">
    <igx-grid #gridRowEditTransaction [data]="data" [primaryKey]="'ProductID'" width="100%" height="500px"
        [rowEditable]="true">
        <igx-column field="ProductID" header="Product ID" editable="false"></igx-column>
        <igx-column field="ReorderLevel" header="ReorderLever" [dataType]="'number'"></igx-column>
        <igx-column field="ProductName" header="ProductName" [dataType]="'string'"></igx-column>
        <igx-column field="UnitsInStock" header="UnitsInStock" [dataType]="'number'">
            <ng-template igxCellEditor let-cell="cell">
                <input name="units" [(ngModel)]="cell.value" style="color: black" />
            </ng-template>
        </igx-column>
        <igx-column field="OrderDate" [dataType]="'date'"></igx-column>
        <igx-column field="Discontinued" header="Discontinued" [dataType]="'boolean'"></igx-column>
    </igx-grid>
</div>
```

> [!NOTE]
> �s�ҏW���܂ޕҏW����Ńv���C�}���L�[�̐ݒ�͕K�{�ł��B
> [!NOTE]
> �e��̕ҏW��L���ɂ���K�v�͂���܂���B�O���b�h�� [`rowEditable`]({environment:angularApiUrl}/classes/igxgridcomponent.html#roweditable) �v���p�e�B���g�p����ƃv���C�}���s�ȊO `field` �v���p�e�B���`�������ׂĂ̍s���ҏW�\�ɂȂ�܂��B����̗�̕ҏW�𖳌��ɂ���ꍇ�A[`editable`]({environment:angularApiUrl}/classes/igxcolumncomponent.html#editable) ��̓��͂� false �ɐݒ肵�܂��B


```typescript

import { Component, ViewChild } from "@angular/core";
import { data } from "./data";

import { IgxGridComponent } from "igniteui-angular";

@Component({
    selector: "app-grid-row-edit",
    styleUrls: [`grid-row-editing-sample.component.css`],
    templateUrl: "grid-row-editing-sample.component.html"
})
export class GridRowEditSampleComponent {
    @ViewChild("gridRowEdit", { read: IgxGridComponent }) public gridRowEdit: IgxGridComponent;

    public data: any[];

    constructor() {
        this.data = data;
    }
}

```

> [!NOTE]
> �O���b�h�́A�ۗ����̃Z���ύX��ێ�����v���o�C�_�[ [`IgxBaseTransactionService`]({environment:angularApiUrl}/classes/igxbasetransactionservice.html) ���s�X�e�[�g���T�u�~�b�g�܂��̓L�����Z������܂œ����g�p���܂��B

## �z�u

- �I�[�o�[���C�̃f�t�H���g�̈ʒu�͕ҏW���[�h�ōs�̉��ɂ���܂��B
     
- �s�̉��ɃX�y�[�X���Ȃ��ꍇ�A�I�[�o�[���C���s�̏�ɕ\������܂��B
     
- ��ԏ�܂��͉��ɕ\�������ƁA�I�[�o�[���C�͕�����܂ŃX�N���[�����ɂ��̈ʒu��ێ����܂��B

## ����

- �s���ҏW���[�h�̏ꍇ�A�ҏW���p�����܂��B�����s�̃Z�����N���b�N���ꂽ���ǂ����B

- Done �{�^�����N���b�N����ƍs�ҏW���������A�ύX���f�[�^�\�[�X�܂��̓g�����U�N�V�����փT�u�~�b�g���܂��B�X�ɍs���ҏW���[�h���������܂��B

- Cancel �{�^�������N���b�N����ƌ��݂̍s�̂��ׂĂ̕ύX�����ɖ߂��A�s�ҏW���[�h���I�����܂��B

- �s���ҏW���[�h�ɂ���ꍇ�A���̍s�̃Z�����N���b�N����ƌ��݂̍s�ҏW���I�����A�s�̐V�K�̕ύX���T�u�~�b�g (Done �{�^�����N���b�N�����ꍇ�Ɠ���) ���܂��B�t�H�[�J�X�̂���V�����Z�����ҏW�\���ǂ����A�V�����s���ҏW���[�h�ɓ��邩�ǂ����A�Z�����ҏW�ł��Ȃ��ꍇ�͑O�̍s�̂ݕҏW���[�h���I�����܂��B

- �s���ҏW���[�h�̎��ɃO���b�h���X�N���[�������ƍs���\���̈�O�ɂȂ�܂����A�O���b�h�͕ҏW���[�h�̂܂܂ł��B�O���b�h���X�N���[������ƍs���Ăѕ\������čs�͕ҏW���[�h�̂܂܂ɂȂ�܂��B

- �ҏW�����e�Z���͍s�ҏW���I������܂ŕύX�X�^�C�����擾���܂��B�O���b�h���g�����U�N�V�����Œ񋟂���Ȃ��ꍇ�̓���ł��B�g�����U�N�V�������L���ȏꍇ�A���ׂĂ̕ύX���R�~�b�g�����܂ŃZ���ҏW�X�^�C�����K�p����܂��B


## �L�[�{�[�h �i�r�Q�[�V����

- `Enter` and `F2` ���s�ҏW���[�h�ɓ���܂��B

- `Esc` ���s�ҏW���[�h���I�����A�s�̕ҏW���[�h���ɕύX���ꂽ������̃Z���̕ύX���T�u�~�b�g���܂���B

- `Tab` �͍s�̕ҏW�\�ȃZ�����玟�̃Z���փt�H�[�J�X���ړ��A�E�[�̕ҏW�\�ȃZ������ CANCEL �� Done �{�^���ֈړ����܂��BDONE �{�^������̃i�r�Q�[�V�����͌��݂̕ҏW�s���ŕҏW�\�ȃZ���ֈړ����܂��B


## �@�\�̓���

- ���ׂẴf�[�^�ύX����͍s�ύX������I�����A���݂̍s�̕ύX���T�u�~�b�g���܂��B���בւ��A�O���[�v�̕ύX�A�t�B���^�����O�����A�y�[�W���O�Ȃǂ��܂܂�܂��B

- �s�ҏW���I��������ɏW�v���X�V����܂��B���l�ɕ��בւ���t�B���^�����O�Ȃǂ̑��̋@�\���L���ɂȂ�܂��B

- �O���[�v�s�̓W�J�Ək���͌��݂̍s�̕ҏW���I�����܂���B


## �s�ҏW�I�[�o�[���C�̃J�X�^�}�C�Y

### �e�L�X�g�̃J�X�^�}�C�Y

`igxRowEditTextDirective` ���g�p�����s�ҏW�I�[�o�[���C�̃e�L�X�g�̃J�X�^�}�C�Y���\�ł��B
`rowChangesCount` �v���p�e�B�����J����ĕύX���ꂽ�Z���̃J�E���g��ێ����܂��B

```html
<ng-template igxRowEditText let-rowChangesCount>
	Changes: {{rowChangesCount}}
</ng-template>
 ```

 ### �{�^���̃J�X�^�}�C�Y
`igxRowEditActionsDirective` ���g�p���čs�ҏW�I�[�o�[���C�̃{�^���̃J�X�^�}�C�Y���\�ł��B
�L�[�{�[�h �i�r�Q�[�V�����Ƀ{�^�����܂߂�ꍇ�A�e�{�^���� `igxRowEditTabStopDirective` ���K�v�ł��B

 ```typescript
 <ng-template igxRowEditActions let-endRowEdit>
	<button igxButton igxRowEditTabStop (click)="endRowEdit(false)">Cancel</button>
	<button igxButton igxRowEditTabStop (click)="endRowEdit(true)">Apply</button>
</ng-template>
 ```

## API

### igxGrid ����

* [rowEditable]({environment:angularApiUrl}/classes/igxgridcomponent.html#roweditable)

### igxGrid �o��

* [onRowEditDone]({environment:angularApiUrl}/classes/igxgridcomponent.html#onroweditdone)
* [onRowEditCancel]({environment:angularApiUrl}/classes/igxgridcomponent.html#onroweditcancel)

### igxGrid ���\�b�h

* [endRowEdit]({environment:angularApiUrl}/classes/igxgridcomponent.html#endrowedit)


### ���̑��̃��\�[�X
<div class="divider--half"></div>

* [Grid �̊T�v](grid.md)
* [Grid �ҏW](grid_editing.md)
* [Grid �g�����U�N�V����](grid_transactions.md)