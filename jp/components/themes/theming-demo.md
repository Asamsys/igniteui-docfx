---
title: �e�[�} �f��
_description: Ignite UI for Angular �́ASASS �@�\�� mixins �ŃA�v���P�[�V�����S�̂���ѓ��蕔�����ŏ����̃R�[�h�ŃX�^�C���ݒ�ł��܂��B
_keywords: Ignite UI for Angular, Angular Theming �R���|�[�l���g, Angular Theming, Ignite UI for Angular �R���|�[�l���g, Ignite for Agular Themes, �O���[�o�� �e�[�}, �R���|�[�l���g �e�[�}
_language: ja
---

## �e�[�} �f��
**Ignite UI for Angular Theming** �́A�O���[�o���ݒ�ŃA�v���P�[�V�����S�̂̃e�[�}���J�X�^�}�C�Y���Ă��ׂĂ̊���̗v�f�ɓK�p�A���邢�̓R���|�[�l���g�ʂɃe�[�}�����ꂼ��K�p���邱�Ƃ��ł��܂��B

### �f��
<div class="sample-container" style="height: 650px">
    <iframe id="theme-chooser-iframe" seamless width="100%" height="100%" frameborder="0" src="{environment:demosBaseUrl}/theme-chooser" onload="onSampleIframeContentLoaded(this);"></iframe>
</div>
<div>
    <button data-localize="stackblitz" class="stackblitz-btn" data-iframe-id="theme-chooser-iframe" data-demos-base-url="{environment:demosBaseUrl}">stackblitz �ŊJ��
    </button>
</div>
<div class="divider--half"></div>


### �f�t�H���g �e�[�}

**�f�t�H���g�̃e�[�}**�́A**Ignite UI for Angular �R���g���[��**�̂��ׂẴR���|�[�l���g�̃X�^�C����ݒ肵�܂��B�͂��߂� `styles.scss` �t�@�C���ɐݒ肵�܂��B

```scss
// import first the IgniteUI themes library
@import "~igniteui-angular/lib/core/styles/themes/index";

// Don't forget to include the igx-core first
@include igx-core();

// the default color palette is passed to the global theme
@include igx-theme($default-palette);
```

�ȉ��͏�L�R�[�h �X�j�y�b�g�̌��ʂł��B

<div class="sample-container" style="height: 650px">
    <iframe id="default-theme-sample-iframe" seamless width="100%" height="100%" frameborder="0" src="{environment:demosBaseUrl}/default-theme-sample" onload="onSampleIframeContentLoaded(this);"></iframe>
</div>
<div>
    <button data-localize="stackblitz" class="stackblitz-btn" data-iframe-id="default-theme-sample-iframe" data-demos-base-url="{environment:demosBaseUrl}"> stackblitz �ŊJ��
    </button>
</div>
<div class="divider--half"></div>

�R���|�[�l���g�̊O�ς�ύX�������ꍇ��**�f�t�H���g �e�[�}**���A�v���P�[�V������ UI �ɍ���Ȃ��ꍇ�́A**Ignite UI for Angular Theming** ���g�p���đ����� CSS �t�@�C�����������ɃX�^�C���ݒ肪�ȒP�ɂł��܂��B

### �J�n

�͂��߂ɁA**SASS functions �� mixins** ������q�ɂȂ��Ă���**�e�[�} ���[�e�B���e�B**���C���|�[�g���܂��B
���z�I�ȃR�[�h�\���́A�ʁX�̃f�B���N�g��**�e�[�} ���W�b�N**�ɔz�u���邱�Ƃł��B

```scss
// styles/dark-theme.scss

@import '~igniteui-angular/lib/core/styles/themes/utilities';

```
<div class="divider--half"></div>

���̃X�e�b�v�́A�J�X�^�}�C�Y����R���|�[�l���g�ƑΉ�����e�[�}�����ׂăC���|�[�g���܂��B

�ȉ����A�v���Ɋ܂܂�܂��B
- **Igx-Grid** �� `paging` �� **�t�B���^�����O**�B

```scss
// Import grid component and theme styles
@import '~igniteui-angular/lib/core/styles/components/grid/grid-component';
@import '~igniteui-angular/lib/core/styles//components/grid/grid-theme';

// Import grid-paginator component and theme styles
@import '~igniteui-angular/lib/core/styles//components/grid-paginator/grid-paginator-component';
@import '~igniteui-angular/lib/core/styles//components/grid-paginator/grid-paginator-theme';

// Import grid-filtering component and theme styles
@import '~igniteui-angular/lib/core/styles//components/grid-filtering/grid-filtering-component';
@import '~igniteui-angular/lib/core/styles//components/grid-filtering/grid-filtering-theme';

```
- **Igx-Dialog** �̑g�ݍ��� `IgxInputGroupComponent`�B

```scss

// Import dialog-group component and theme styles
@import '~igniteui-angular/lib/core/styles//components/dialog/dialog-component';
@import '~igniteui-angular/lib/core/styles//components/dialog/dialog-theme';

// Import input-group component and theme styles
@import '~igniteui-angular/lib/core/styles//components/input/input-group-component';
@import '~igniteui-angular/lib/core/styles//components/input/input-group-theme';

```

�R���|�[�l���g�̃e�[�}�ݒ�ɕK�v�Ȃ��ׂĂ̋@�\�����邽�߁A�g�p����**�F�p���b�g**���`���邾���ł��B

```scss
// Define the primary color
$dark-color: #282828;

// Define the secondary color
$orange-color: #FFA500;

// Define the palette:
$dark-theme-palette: igx-palette($primary: $dark-color, $secondary: $orange-color);
```

���ɃA�v���ɐV�����X�^�C����ݒ肵�܂��B
<div class="divider--half"></div>

### �e�[�}�̐ݒ�

**�e�[�}�̐ݒ�**�́A�v���C�}������уZ�J���_���̐F�̈قȂ�V�F�[�h���R���|�[�l���g �p�[�c�ɓK�p���܂��B[**Ignite UI for Angular Themes**](https://staging.infragistics.local/products/ignite-ui-angular/docs/sass/) �̃w���v�ŃX�^�C���ݒ�\�ȃR���|�[�l���g �p�[�c���m�F�ł��܂��B

�K�p���� **�R���|�[�l���g �e�[�}**���`���܂��B

#### �R���|�[�l���g �e�[�}�̒�`
<div class="divider--half"></div>

- [**Igx-Grid-Theme**](https://staging.infragistics.local/products/ignite-ui-angular/docs/sass/#function-igx-grid-theme)

```scss
// Define dark theme for the dialog
$dark-grid-theme: igx-grid-theme(
  $palette: $dark-theme-palette,
  $content-background: igx-color($dark-theme-palette, "secondary", 100),
  $header-background: igx-color($dark-theme-palette, "primary", 500),
  $header-text-color: igx-color($dark-theme-palette, "secondary", 600),
  $cell-selected-background: igx-color($dark-theme-palette, "secondary", 600),
  $cell-selected-text-color: igx-color($dark-theme-palette, "primary", 600),
  $row-hover-background: igx-color($dark-theme-palette, "primary", 100),
  $header-border-color: igx-color($dark-theme-palette, "primary", 600)
);
```

- [**Igx-Dialog-Theme**](https://staging.infragistics.local/products/ignite-ui-angular/docs/sass/#themes-function-igx-dialog-theme)

```scss

// Define dark theme for the dialog
$dark-dialog-theme: igx-dialog-theme(
  $palette: $dark-theme-palette,
  $background: igx-color($dark-theme-palette, "primary", 100),
  $title-color: igx-color($dark-theme-palette, "secondary", 500),
  $message-color: igx-color($dark-theme-palette, "secondary", 600)
);

```

- [**Igx-Input-Group-Theme**](https://staging.infragistics.local/products/ignite-ui-angular/docs/sass/#themes-function-igx-input-group-theme)

```scss
// Define dark theme for the input-group
$dark-input-group-theme: igx-input-group-theme(
  $palette: $dark-theme-palette,
  $box-background:  igx-color($dark-theme-palette, "primary", 100),
  $disabled-border-color: igx-color($dark-theme-palette, "primary", 500),
  $box-disabled-background: igx-color($dark-theme-palette, "secondary", 100),
  $hover-bottom-line-color: igx-color($dark-theme-palette, "secondary", 700),
  $focused-bottom-line-color: igx-color($dark-theme-palette, "secondary", 700),
  $focused-text-color: igx-color($dark-theme-palette, "secondary", 500),
  $idle-text-color: igx-color($dark-theme-palette, "secondary", 700)
);
```

����Ŋ������܂����B

�A�v���̊e�R���|�[�l���g�Ƀe�[�}���쐬���܂����B�Ō�ɓK�p���܂��B

#### �R���|�[�l���g �e�[�}�̓K�p
�z�X�g�v�f�� `class` ��**�e�[�} �N���X**�Ńo�C���h���܂��B

```typescript
@HostBinding("class")
public themesClass = "dark-theme";
```
<div class="divider--half"></div>

���Ƀz�X�g�v�f��**�e�[�} �N���X**���l�X�g�����V���� SCSS �t�@�C���Ƀe�[�}��K�p�����R���|�[�l���g���܂݂܂��B

```scss
// styles/dark-themes-class.scss
@import 'dark-theme';

:host {
    display: block;
    margin: 16px;
    box-shadow: igx-elevation($elevations, 12);

    &.dark-theme {
      background: $dark-color;
        ::ng-deep {
          @include igx-grid($dark-grid-theme);
          @include igx-snackbar($dark-snackbar-theme);
          @include igx-input-group($dark-input-group-theme);
          @include igx-grid-paginator($dark-grid-paginator-theme);
          @include igx-button($dark-button-theme);
          @include igx-dialog($dark-dialog-theme);
          @include igx-grid-filtering($dark-grid-filtering-theme);
          @include igx-button-group($dark-button-group-theme);
      }
    }
}
```
���ʂ͈ȉ��ł��B

<div class="sample-container" style="height: 650px">
    <iframe id="dark-theme-sample-iframe" seamless width="100%" height="100%" frameborder="0" src="{environment:demosBaseUrl}/dark-theme-sample" onload="onSampleIframeContentLoaded(this);"></iframe>
</div>
<div>
    <button data-localize="stackblitz" class="stackblitz-btn" data-iframe-id="dark-theme-sample-iframe" data-demos-base-url="{environment:demosBaseUrl}"> stackblitz �ŊJ��
    </button>
</div>
<div class="divider--half"></div>

*utilities*�A�R���|�[�l���g mixins �ƃe�[�}�֐����C���|�[�g���A�e�[�}���`���ēK�p���܂��B**Ignite UI for Angular Theming** �ŃA�v�����X�^�C���ݒ肷�邽�߂̎菇������܂��B

### �e�[�}�̑I��
��L�T���v���́A�e�R���|�[�l���g�� 1 �̃e�[�}��ݒ肵�܂����B

**Ignite UI for Angular �R���|�[�l���g**�ɂ��̑��̃e�[�}���`����ꍇ�́A**�e�[�}**��ǉ��ł��܂��B

�ύX�����������邾���ł��B
- SCSS �t�@�C�����쐬���ăe�[�}���܂ރN���X���`���܂��B

```scss
// styles/themes-classes.scss
@import 'themes';

:host {
    display: block;
    margin: 16px;
    box-shadow: igx-elevation($elevations, 12);

    // Set the light themes for the components.
    &.light-theme {
      background: $light-color;
      ::ng-deep {
        @include igx-grid($light-grid);
        @include igx-snackbar($light-snackbar);
        @include igx-input-group($light-input-group);
        @include igx-grid-paginator($light-grid-paginator);
        @include igx-button($light-button);
        @include igx-dialog($light-dialog);
        @include igx-grid-filtering($light-grid-filtering);
        @include igx-button-group($light-button-group);
      }
    }
    ...
  }
```

<div class="divider--half"></div>

- �z�X�g�v�f�� `class` �𑀍삷��֐����g���K�[����C�x���g��ݒ肵�܂��B

```html
<!-- Adding igxButton that triggers a dropdown with the theme options -->
<div class = "grid_wrapper" igxOverlayOutlet #outlet>
    <div class="grid-options" igxLayout igxLayoutDir="row" igxLayoutWrap="wrap">
        <button igxButton="raised" class="addProdBtn" (click)="openDialog()">Add New Product</button>
        <button class="drop-down-button" igxButton="raised" (click)="toggleDropDown($event, dropdown)">Themes</button>
        <igx-drop-down #dropdown class="theme-chooser">
            <igx-drop-down-item class="light-theme-option" [igxDropDownItemNavigation]="dropdown" (click)="selectTheme(THEME.LIGHT)">
            </igx-drop-down-item>
            <igx-drop-down-item class="dark-theme-option" [igxDropDownItemNavigation]="dropdown" (click)="selectTheme(THEME.DARK)">
            </igx-drop-down-item>
            <igx-drop-down-item class="black-theme-option" [igxDropDownItemNavigation]="dropdown" (click)="selectTheme(THEME.BLACK)">
            </igx-drop-down-item>
        </igx-drop-down>
    </div>
...
</div>
```

<div class="divider--half"></div>

**�e�[�} �N���X** ��\���f�[�^����уz�X�g�v�f�� `class` �Z���N�^�[�𑀍삷��֐���ǉ����܂��B

```typescript

// Enumeration that will represent the themes classes

export enum THEME {
    LIGHT = "light-theme",
    DARK = "dark-theme",
    BLACK = "black-theme"
}

@Component({
    selector: "app-theme-chooser-sample",
    styleUrls: ["./theme-chooser-sample.component.scss"],
    templateUrl: "./theme-chooser-sample.component.html"
})
export class ThemeChooserSampleComponent implements OnInit {
    // Provide a reference to the themes classes
    public THEME: typeof THEME = THEME;
    // Bind the host element class with the themes class and set a default value
    @HostBinding("class")
    public themesClass: THEME = THEME.LIGHT;
    ...
    // Provide a function that manipulates the the class reference
    public selectTheme(theme: THEME) {
        this.themesClass = theme;
    }
    ...

```
<div class="divider--half"></div>

`click` �C�x���g�݂̂Œ�`�ς݃e�[�}���ȒP�ɕύX�ł��܂��B

<div class="sample-container" style="height: 650px">
    <iframe id="theme-chooser-iframe" seamless width="100%" height="100%" frameborder="0" src="{environment:demosBaseUrl}/theme-chooser" onload="onSampleIframeContentLoaded(this);"></iframe>
</div>
<div>
    <button data-localize="stackblitz" class="stackblitz-btn" data-iframe-id="theme-chooser-iframe" data-demos-base-url="{environment:demosBaseUrl}"> stackblitz �ŊJ��
    </button>
</div>

### ���̑��̃��\�[�X
<div class="divider--half"></div>

* [�O���[�o�� �e�[�}](global-theme.md)
* [�R���|�[�l���g �e�[�}](component-themes.md)
* [�J���[ �p���b�g](palette.md)
* [�O���b�h](grid.md)
* [�y�[�W���O](grid_paging.md)
* [�t�B���^�����O](grid_filtering.md)
* [�_�C�A���O](dialog.md)
* [�C���v�b�g �O���[�v](input_group.md)
* [�X�i�b�N�o�[](snackbar.md)
* [�{�^��](button.md)
* [�{�^�� �O���[�v](button_group.md)