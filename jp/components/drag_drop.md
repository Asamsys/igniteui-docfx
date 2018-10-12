---
title: �h���b�O �A���h �h���b�v
_description: Ignite UI for Angular Drag and Drop �f�B���N�e�B�u���g�p���� DOM �v�f�̈ʒu���ړ��ł��܂��B
_keywords: Ignite UI for Angular, UI �R���g���[��, Angular �E�B�W�F�b�g, web �E�B�W�F�b�g, UI �E�B�W�F�b�g, Angular, �l�C�e�B�u Angular �R���|�[�l���g �X�C�[�g, �l�C�e�B�u Angular �R���g���[��, �l�C�e�B�u Angular �R���|�[�l���g ���C�u����, Angular Scrollbar �R���|�[�l���g,  Angular Drag and Drop �f�B���N�e�B�u
_language: ja
---

## �h���b�O �A���h �h���b�v
<p class="highlight">Ignite UI for Angular Drag and Drop �f�B���N�e�B�u�́A�y�[�W�̗v�f�̃h���b�O��L���ɂ��܂��B</p>

#### �f��

�^�C�g�����h���b�O�A���h�h���b�v����p�Y��

<div class="sample-container loading" style="height:325px">
    <iframe id="drag-drop-sample-iframe" src='{environment:demosBaseUrl}/drag-drop-sample' width="100%" height="100%" seamless frameBorder="0" onload="onSampleIframeContentLoaded(this);"></iframe>
</div>
<br/>
<div>
<button data-localize="stackblitz" disabled class="stackblitz-btn" data-iframe-id="drag-drop-sample-iframe" data-demos-base-url="{environment:demosBaseUrl}">view on stackblitz</button>
</div>
<div class="divider--half"></div>

### Drag �f�B���N�e�B�u

Angular �A�v���P�[�V�������̗v�f������ꏊ���瑼�̏ꏊ�փh���b�O����ɂ́A[`igxDrag`]({environment:angularApiUrl}/classes/igxdragdirective.html) �f�B���N�e�B�u���g�p���܂��B[`igxDrop`]({environment:angularApiUrl}/classes/igxdropdirective.html) �f�B���N�e�B�u�Ƒg�ݍ��킹�ăh���b�O�����v�f�̔z�u��C���^���N�e�B�u�ȃA�v���P�[�V�������쐬�ł��܂��B

#### ��{�\��

[`igxDrag`]({environment:angularApiUrl}/classes/igxdragdirective.html) �f�B���N�e�B�u�́A�e���v���[�g�ɒǉ����� DOM �v�f�ɓK�p�ł��܂��B

```html
<div igxDrag>Drag me</div>
```

#### DOM ����

���[�U�[�� 5px �����ꂩ�̕����փX���C�v����ƃf�t�H���g�Ńh���b�O������J�n���܂��B�����łȂ��ꍇ�́A�C���^���N�V�������N���b�N�Ƃ��Č��Ȃ���A[`dragClicked`]({environment:angularApiUrl}/classes/igxdragdirective.html#dragclicked) �C�x���g���������܂��B

�h���b�O���Ƀh���b�O �S�[�X�g�v�f���������A�}�E�X�J�[�\���܂��̓^�b�`�C���^���N�V�����Ƌ��Ɉړ����܂��B���̗v�f�͕\�����ꂽ�܂܂ł����A[`hideBaseOnDrag`]({environment:angularApiUrl}/classes/igxdragdirective.html#hidebaseondrag) �Ńh���b�O�J�n���Ɏ����I�ɔ�\���ɂł��܂��B

�h���b�O�́A[`dragStart`]({environment:angularApiUrl}/classes/igxdragdirective.html#dragstart) �C�x���g�� [`cancel`]({environment:angularApiUrl}/interfaces/idragstarteventargs.html#cancel) �v���p�e�B�� true �ɐݒ肵�ăL�����Z���ł��܂��B�f�t�H���g�̃h���b�O ���W�b�N���L�����Z�����܂��B

���[�U�[�������[�X������A�}�E�X/�^�b�` �h���b�O �S�[�X�g�v�f�� DOM ����폜����A[`hideBaseOnDrag`]({environment:angularApiUrl}/classes/igxdragdirective.html#hidebaseondrag) ���L���ȏꍇ�A���̗v�f���Ăѕ\������� [`dragEnd`]({environment:angularApiUrl}/classes/igxdragdirective.html#dragend) ����������܂��B[`animateOnRelease`]({environment:angularApiUrl}/classes/igxdragdirective.html#animateonrelease) ���͂� `true` �ɐݒ肷��ƁA�Ō�Ƀh���b�O�����ʒu���猳�̗v�f�̈ʒu�֖߂��h���b�O �S�[�X�g�̃f�t�H���g �A�j���[�V�����̊�����Ɏ��s���܂��B�h���b�O �S�[�X�g�͍폜����A[`returnMoveEnd`]({environment:angularApiUrl}/classes/igxdragdirective.html#returnmoveend) �C�x���g����������܂��B

#### �g�p���@
```html
<div igxDrag [hideBaseOnDrag]="true" [animateOnRelease]="true" *ngFor="let elem of draggableElems" >
    <span [style.margin]="'auto'">{{elem.label}}</span>
</div>
```

### Drop �f�B���N�e�B�u

[`igxDrag`]({environment:angularApiUrl}/classes/igxdragdirective.html) �f�B���N�e�B�u���g�p���ăh���b�O����Ă���v�f��̈�ɔz�u����ꍇ�A[`igxDrop`]({environment:angularApiUrl}/classes/igxdropdirective.html) ���g�p���܂��B�v�f���h���b�v�̈�ɓ��������ǂ����A���̌�̈���Ń����[�X����Ă��邩�����肷�邽�߂Ƀ��[�U�[���g�p�ł���C�x���g��񋟂��܂��B

#### ��{�\��
[`igxDrop`]({environment:angularApiUrl}/classes/igxdropdirective.html) �f�B���N�e�B�u�� [`igxDrag` �Ɠ��l�� DOM �v�f�ɓK�p�ł��܂��B 

````html
<div igxDrop>Drop here</div>
````

[`igxDrop`]({environment:angularApiUrl}/classes/igxdropdirective.html) �f�B���N�e�B�u�Ƀh���b�v���� [`igxDrag`]({environment:angularApiUrl}/classes/igxdragdirective.html) �v�f�́A�C���X�^���X������ [`igxDrop`]({environment:angularApiUrl}/classes/igxdropdirective.html) �����v�f�̎q�Ƃ��ĕt�������郍�W�b�N���f�t�H���g�Œ񋟂���܂��B[`igxDrop`]({environment:angularApiUrl}/classes/igxdropdirective.html) �f�B���N�e�B�u�� [`onDrop`]({environment:angularApiUrl}/classes/igxdropdirective.html#ondrop) �C�x���g���L�����Z�����ăI�[�o�[���C�h�ł��܂��B[`onDrop`]({environment:angularApiUrl}/classes/igxdropdirective.html#ondrop) �C�x���g���񋟂��� [`cancel`]({environment:angularApiUrl}/classes/igxdropeventargs.html#cancel) ������ݒ肵�čs�����Ƃ��ł��܂��B

�h���b�v ���W�b�N���`���A[`igxDrag`]({environment:angularApiUrl}/classes/igxdragdirective.html) �� [`animateOnRelease`]({environment:angularApiUrl}/classes/igxdragdirective.html#animateonrelease) ���͂� true �ɐݒ肵���ꍇ�ADOM ���슮����� [`igxDrag`]({environment:angularApiUrl}/classes/igxdragdirective.html) �� [`dropFinished()`]({environment:angularApiUrl}/classes/igxdragdirective.html#dropfinished) ���\�b�h���Ăяo�����Ƃ���������܂��B[`igxDrag`]({environment:angularApiUrl}/classes/igxdragdirective.html) �ɒʒm���Ċ֘A����z�u�� DOM �̐V�����ʒu�ɍX�V���邱�Ƃɂ��A�������A�j���[�V���������܂��B

[`onDrop`]({environment:angularApiUrl}/classes/igxdropdirective.html#ondrop) �f�t�H���g�̃h���b�v ���W�b�N���L�����Z���̗�B

````html
<div igxDrop (onDrop)="onElemDrop($event)">Drop here</div>
````

````ts
public onElemDrop(event: IgxDropEventArgs) {
    event.cancel = true; // This cancels the default drop logic
    // ...
    // Custom implementation logic
    // ...

    // This is required to tell the dragged element the dropping has finished, so it can return to the new location/old location.
    // It can be called anywhere in the code as well.
    event.drag.dropFinished(); 
}
````

#### ���x�Ȑݒ�
1 �̗v�f�� [`igxDrag`]({environment:angularApiUrl}/classes/igxdragdirective.html) �� [`igxDrop`]({environment:angularApiUrl}/classes/igxdropdirective.html) �����̃f�B���N�e�B�u���g�p�ł��܂��B�������A���̗v�f�� [`igxDrop`]({environment:angularApiUrl}/classes/igxdropdirective.html) �f�B���N�e�B�u�� [`onDrop`]({environment:angularApiUrl}/classes/igxdropdirective.html#ondrop) �C�x���g���L�����Z�����ăh���b�v����Ă���Ƃ��̓J�X�^�� ���W�b�N���g�p���Ă��������B

#### �g�p���@
````html
<div class="dropArea" igxDrop (onEnter)="onAreaEnter()" (onLeave)="onAreaLeave()">
    <span *ngIf="!elementInsideArea">Drag here.</span>
    <span *ngIf="elementInsideArea">Release to put element here.</span>
</div>
````

````ts
//App component...
public onAreaEnter() {
    this.elementInsideArea = true;
    this.changeDetectionRef.detectChanges();
}
public onAreaLeave() {
    this.elementInsideArea = false;
    this.changeDetectionRef.detectChanges();
}
//...
````


### API
* [IgxDragDirective]({environment:angularApiUrl}/classes/igxdragdirective.html)
* [IgxDropDirective]({environment:angularApiUrl}/classes/igxdropdirective.html)

### ���t�@�����X

<div class="divider--half"></div>
�R�~���j�e�B�ɎQ�����ĐV�����A�C�f�A������Ă��������B

- [Ignite UI for Angular** �t�H�[����** (�p��) ](https://www.infragistics.com/community/forums/f/ignite-ui-for-angular)
- [Ignite UI for Angular **GitHub** (�p��) ](https://github.com/IgniteUI/igniteui-angular)
