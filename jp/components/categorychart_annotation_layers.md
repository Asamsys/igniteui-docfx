---
title: �J�e�S�� �`���[�g���߂ƃI�[�o�[���C
_description: Ignite UI for Angular Category Chart �R���|�[�l���g�͕��G�ȃf�[�^ �r�W���A���C�[�[�V������ API �ɂ���Ċȑf���ł��܂��B���[�U�[���f�[�^�̃R���N�V�����܂��̓R���N�V�����̃O���[�v�Ƀo�C���h���A�f�[�^���w�肷��v���p�e�B��ݒ��A�`���[�g �R���g���[�����c��̍�Ƃ��������܂��B
_keywords: Ignite UI for Angular, Angular, �l�C�e�B�u Angular �R���|�[�l���g �X�C�[�g, �l�C�e�B�u Angular �R���g���[��, �l�C�e�B�u Angular �R���|�[�l���g, �l�C�e�B�u Angular �R���|�[�l���g ���C�u����, Angular �`���[�g, Angular �`���[�g �R���g���[��, Angular �`���[�g��, Angular Grid �R���|�[�l���g, Angular Chart �R���|�[�l���g, Angular Category Chart
_language: ja
---
## �J�e�S�� �`���[�g���߂ƃI�[�o�[���C

���̃g�s�b�N�ł́A`igx-category-chart` �̒��߂�C���^���N�V�����ɂ��Đ������܂��B

### �f��
<div class="sample-container" style="height: 550px">
    <iframe id="category-chart-annotations-and-overlays-iframe" src='{environment:demosBaseUrl}/category-chart-annotations-and-overlays' width="100%" height="100%" seamless frameBorder="0" onload="onSampleIframeContentLoaded(this);"></iframe>
</div>
<div>
    <button data-localize="stackblitz" class="stackblitz-btn"   data-iframe-id="category-chart-annotations-and-overlays-iframe" data-demos-base-url="{environment:demosBaseUrl}"> StackBlitz �ŊJ��
    </button>
</div>
<div class="divider--half"></div>

## �I�[�o�[���C �^�C�v

### �\�������C���[

Crosshair Layer �́A�e�^�[�Q�b�g �V���[�Y�̎��ۂ̒l�Ɉ�v����\������񋟂��܂��BCrosshair �^�C�v�́AHorizontal�AVertical�ABoth ������܂��B

```html
<igx-category-chart
    [dataSource]="data"
    displayCrosshairs="Horizontal"
    snapCrosshairsToData="true"
    displayCrosshairAxisAnnotations="true">
</igx-category-chart>
```

### �J�e�S�� �c�[���`�b�v ���C���[

�J�e�S�� �c�[���`�b�v ���C���[�́A�J�e�S�������g�p����V���[�Y�p�ɃO���[�v�����ꂽ�c�[���`�b�v��\�����܂��B

```html
<igx-category-chart
    [dataSource]="data"
    tooltipType="Category">
</igx-category-chart>
```

### �A�C�e�� �c�[���`�b�v ���C���[

�A�C�e�� �c�[���`�b�v ���C���[�́A���ׂẴ^�[�Q�b�g �V���[�Y�Ƀc�[���`�b�v��\���܂��B

```html
<igx-category-chart
    [dataSource]="data"
    tooltipType="Item">
</igx-category-chart>
```

### �J�e�S�����ڋ����\�����C���[

Category Item Highlight Layer ���C���[�́A���̈ʒu�ŎȖ͗l�V�F�C�v�܂��̓}�[�J�[��`�悷�邱�Ƃɂ��A�J�e�S�������g�p����V���[�Y���̍��ڂ������\�����܂��B

```html
<igx-category-chart
    [dataSource]="data"
    highlightItemUnderCursor="true">
</igx-category-chart>
```

### �J�e�S�������\�����C���[

�J�e�S�����܂��̓`���[�g���̂��ׂẴJ�e�S�����ɑ΂��钍�߃��C���[��\���܂��B�J�[�\���ʒu�ɍł��߂����̃G���A���Ƃ炷�V�F�C�v��`�悵�܂��B

```html
<igx-category-chart
    [dataSource]="data"
    highlightCategoryUnderCursor="true">
</igx-category-chart>
```

## ���߃^�C�v

### �ŏI�l���C���[

�ŏI�l���C���[�́A�V���[�Y�ɕ\�����ꂽ�ŏI�l�̎��ɉ������N�C�b�N�r���[���T�|�[�g���܂��B

```html
<igx-category-chart
    [dataSource]="data"
    displayFinalValueAnnotation="true">
</igx-category-chart>
```

### �R�[���A�E�g ���C���[

Callout Layer �́AX/Y �ʒu�ɃR�[���A�E�g��\�����܂��B���߂Ƀz�o�[�����ۂɃ��x���ƒǉ��R���e���c���c�[���`�b�v�ŕ\���ł��܂��B

> ��:  Category ���g�p���� `eventsXMemberPath` �����l�C���f�b�N�X�܂��͎��Ԏ��̎��Ԓl���|�C���g����K�v������܂��B

```html
<igx-category-chart
    [dataSource]="data"
    displayEventAnnotations="true"
    [eventsDataSource]="calloutData"
    eventsXMemberPath="index"
    eventsYMemberPath="yValue"
    eventsTitleMemberPath="title"
    eventsContentMemberPath="content">
</igx-category-chart>
```
