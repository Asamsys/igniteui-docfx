---
title: �A�b�v�f�[�g �K�C�h
_description: ���̃g�s�b�N�ł́A�V�����o�[�W������ Ignite UI for Angular ���C�u�����ɃA�b�v�f�[�g������@�ɂ��Ă��Љ�܂��B
_keywords: Ignite UI for Angular, �A�b�v�f�[�g, npm �p�b�P�[�W, �o�[�W����, UI �R���g���[��, Angular �E�B�W�F�b�g, web �E�B�W�F�b�g, UI �E�B�W�F�b�g, Angular, �l�C�e�B�u Angular �R���|�[�l���g �X�C�[�g, �l�C�e�B�u Angular �R���g���[��, �l�C�e�B�u Angular �R���|�[�l���g ���C�u����
_language: ja
---

## �A�b�v�f�[�g �K�C�h

Ignite UI for Angular [�o�[�W���j���O](https://github.com/IgniteUI/igniteui-angular/wiki/Ignite-UI-for-Angular-versioning) �́A�ŏ��̐������R�[�h���T�|�[�g���� Angular �̃��W���[ �o�[�W�����ŁA2 �Ԗڂ̐����̓��W���[ �o�[�W���� �����[�X�̐����ł��B�d��ȕύX�̓��W���[ �����[�X�ƃ��W���[ �����[�X�̊ԂɃ����[�X�����ꍇ������܂��B
**Ignite UI for Angular** �e�����[�X�̂��ׂĂ̕ύX�̈ꗗ�́A���i [CHANGELOG](https://github.com/IgniteUI/igniteui-angular/blob/master/CHANGELOG.md) ���������������B

Ignite UI for Angular �p�b�P�[�W�� `ng update` Schematics �Ŏ����o�[�W���� �}�C�O���[�V�������T�|�[�g���܂��B����ɂ��A�\���̂��邷�ׂĂ̏d��ȕύX (�Z���N�^�[�̖��O�A�N���X�A@Input/Output �v���p�e�B�̕ύX) ���}�C�O���[�V�������悤�Ƃ��܂��B�������A�}�C�O���[�V�����ł��Ȃ��ύX������ꍇ������܂��B�ʏ킱���̕ύX�̓^�C�v �X�N���v�g �A�v���P�[�V���� ���W�b�N�Ɋ֘A���Ă���A[�ڍ�](#additional-manual-changes)�͈ȉ������m�F���������B

�ŏ��� [**`ng update`**](https://angular.io/cli/update) �R�}���h�����s����
```cmd
ng update
```

> [!NOTE]
> �A�b�v�f�[�g����O�ɂ��ׂĂ̕ύX���R�~�b�g���邱�Ƃ������߂��܂��B 

**Ignite UI for Angular** �p�b�P�[�W���X�V����ɂ́A�ȉ��̃R�}���h�����s���Ă��������B
```cmd
ng update igniteui-angular
```
`Igniteui-angular` �̍X�V���́A@angular/core`, `@angular/cli` and `igniteui-cli` �p�b�P�[�W����v����o�[�W�����ɃA�b�v�f�[�g���Ă��������B 
**Ignite UI CLI** �p�b�P�[�W���A�b�v�f�[�g����ꍇ�́A�ȉ��̃R�}���h�����s���Ă��������B
```cmd
ng update igniteui-cli
```
**Angular Core** �p�b�P�[�W���A�b�v�f�[�g����ꍇ�́A�ȉ��̃R�}���h�����s���Ă��������B
```cmd
ng update @angular/core
```
**Angular CLI** �p�b�P�[�W���A�b�v�f�[�g����ɂ́A�ȉ��̃R�}���h���g�p���Ă��������B
```cmd
ng update @angular/cli
```

## ���̑��̎蓮�̕ύX


�����I�ɃA�b�v�f�[�g�ł��Ȃ��ύX������܂��B�ȉ��̕ύX�̓o�[�W�����Ŕ������邽�߃Z�N�V�������Ƃɕ�����A�A�b�v�f�[�g���K�v�ȏꍇ�́A���݂̃o�[�W��������J�n���Ă���ȍ~�̃A�b�v�f�[�g��K�p��j�܂��B

��: 6.2.4 ���� 7.1.0 �ɃA�b�v�f�[�g����ꍇ�A[6.x .. ����] �Z�N�V��������n�߂ĕύX��K�p���Ă����܂��B

### 7.0.x ���� 7.1.x
 * �A�v���P�[�V������ IgxGrid �̏W�v���g�p����ꍇ�A`IgxSummaryOperand.operate()` ���\�b�h������f�[�^�ƂƂ��ɏ��ԂɌĂяo����ďW�v�s�ɕK�v�ȍ������v�Z���܂��B�J�X�^���W�v�I�y�����h�́A���\�b�h����ɓK�؂Ȓ����� IgxSummaryResult �̔z���Ԃ��܂��B

	�o�[�W���� 7.1 �ȑO:
```typescript	
export class CustomSummary extends IgxNumberSummaryOperand {
	public operate(data?: any[]): IgxSummaryResult[] {
		return [{
			key: 'average',
			label: 'average',
			summaryResult: IgxNumberSummaryOperand.average(data).toFixed(2)
		}];
	}
}
```

	�o�[�W���� 7.1 �ȍ~:
```typescript
export class CustomSummary extends IgxNumberSummaryOperand {
	public operate(data?: any[]): IgxSummaryResult[] {
		return [{
			key: 'average',
			label: 'average',
			summaryResult: data.length ?  IgxNumberSummaryOperand.average(data).toFixed(2) : null
		}];
	}
}
```

### 6.0.x ���� 6.1.x

* �A�v���P�[�V������ IgxCombo �R���g���[�����g�p����ꍇ�A`itemsMaxWidth` �I�v�V������ݒ肵�A���̃I�v�V������ `itemsWidth` �ɕύX���Ă��������B