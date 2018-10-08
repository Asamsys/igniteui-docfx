---
title: �J�e�S�� �`���[�g���߂ƃI�[�o�[���C
_description: Ignite UI for Angular Financial Chart �R���|�[�l���g�́A�V���v���Œ����I�� API ���g�p���ăt�@�C�i���V���� �f�[�^��\�����܂��B���[�U�[���f�[�^�Ƀo�C���h��A�`���[�g�̓f�[�^�̉����I�v�V�����𕡐��񋟂��܂��B
_keywords: Ignite UI for Angular, Angular, �l�C�e�B�u Angular �R���|�[�l���g �X�C�[�g, �l�C�e�B�u Angular �R���g���[��, �l�C�e�B�u Angular �R���|�[�l���g, �l�C�e�B�u Angular �R���|�[�l���g ���C�u����, Angular �`���[�g, Angular �`���[�g �R���g���[��, Angular �`���[�g��, Angular Grid �R���|�[�l���g, Angular Chart �R���|�[�l���g, Angular Financial Chart
_language: ja
---
## �J�e�S�� �`���[�g���߂ƃI�[�o�[���C

���̃g�s�b�N�ł́A`igx-financial-chart` �̒��߂�C���^���N�V�����ɂ��Đ������܂��B

### �f��
<div class="sample-container" style="height: 550px">
    <iframe id="financial-chart-annotations-and-overlays-iframe" src='{environment:demosBaseUrl}/financial-chart-annotations-and-overlays' width="100%" height="100%" seamless frameBorder="0" onload="onSampleIframeContentLoaded(this);"></iframe>
</div>
<div>
    <button data-localize="stackblitz" class="stackblitz-btn"   data-iframe-id="financial-chart-annotations-and-overlays-iframe" data-demos-base-url="{environment:demosBaseUrl}">StackBlitz �ŕ\���J��
    </button>
</div>
<div class="divider--half"></div>

## �I�[�o�[���C �^�C�v

### �\�������C���[

Crosshair Layer �́A�e�^�[�Q�b�g �V���[�Y�̎��ۂ̒l�Ɉ�v����\������񋟂��܂��BCrosshair �^�C�v�́AHorizontal�AVertical�ABoth ������܂��B

```html
<igx-financial-chart
    [dataSource]="data"
    width="850px"
    height="600px"
    showCrosshairs="Horizontal"
    snapCrosshairsToData="true"
    displayCrosshairAxisAnnotations="true">
</igx-financial-chart>
```

### �J�e�S�� �c�[���`�b�v ���C���[

�J�e�S�� �c�[���`�b�v ���C���[�́A�J�e�S�������g�p����V���[�Y�p�ɃO���[�v�����ꂽ�c�[���`�b�v��\�����܂��B

```html
<igx-financial-chart
    [dataSource]="data"
    width="850px"
    height="600px"
    tooltipType="Category">
</igx-financial-chart>
```

### �A�C�e�� �c�[���`�b�v ���C���[

�A�C�e�� �c�[���`�b�v ���C���[�́A���ׂẴ^�[�Q�b�g �V���[�Y�Ƀc�[���`�b�v��\���܂��B

```html
<igx-financial-chart
    [dataSource]="data"
    width="850px"
    height="600px"
    tooltipType="Item">
</igx-financial-chart>
```

## ���߃^�C�v

### �ŏI�l���C���[

�ŏI�l���C���[�́A�V���[�Y�ɕ\�����ꂽ�ŏI�l�̎��ɉ������N�C�b�N�r���[���T�|�[�g���܂��B

```html
<igx-financial-chart
    [dataSource]="data"
    width="850px"
    height="600px"
    displayFinalValueAnnotation="true">
</igx-financial-chart>
```

### �R�[���A�E�g ���C���[

�R�[���A�E�g ���C���[�́AX/Y �ʒu�ɃR�[���A�E�g��\�����܂��B���߂Ƀz�o�[�����ۂɃ��x���ƒǉ��R���e���c���c�[���`�b�v�ŕ\���ł��܂��B

> ��: X �����[�h���g�p����ۂ� `eventsXMemberPath` �͐��l�C���f�b�N�X���|�C���g����K�v������܂��B���邢�́A`eventsXMemberPath` �����Ԓl�Ƀ|�C���g���Ă��������B

```html
<igx-financial-chart
    [dataSource]="data"
    width="850px"
    height="600px"
    displayEventAnnotations="true"
    [eventsDataSource]="calloutData"
    eventsXMemberPath="index"
    eventsYMemberPath="yValue"
    eventsTitleMemberPath="title"
    eventsContentMemberPath="content">
</igx-financial-chart>
```
