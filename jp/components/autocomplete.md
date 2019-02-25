---
title: �I�[�g�R���v���[�g �f�B���N�e�B�u
_description: igxAutocomplete �f�B���N�e�B�u�́A���I�v�V�����̃p�l����\�����邱�Ƃɂ��e�L�X�g���͂����シ����@��񋟂��܂��B
_keywords: Ignite UI for Angular, UI �R���g���[��, Angular �E�B�W�F�b�g, web �E�B�W�F�b�g, UI �E�B�W�F�b�g, Angular, �l�C�e�B�u Angular �R���|�[�l���g �X�C�[�g, �l�C�e�B�u Angular �R���g���[��, �l�C�e�B�u Angular �R���|�[�l���g ���C�u����, Angular Autocomplete �R���|�[�l���g, Angular Autocomplete �f�B���N�e�B�u, Angular Autocomplete �R���g���[��
_language: ja
---

## Autocomplete
<p class="highlight">

[**igxAutocomplete**]({environment:angularApiUrl}/classes/igxautocompletedirective.html) �f�B���N�e�B�u�� [igxDropDown]  ({environment:angularApiUrl}/classes/igxdropdowncomponent.html) �ƌ��I�v�V������\�����ăe�L�X�g���͂����シ����@��񋟂��܂��B���́A�e�L�X�g���͂̊J�n���A�܂��� `����/`�����` �L�[���g�p���ĕ\�����܂��B

�f�t�H���g�ōŏ��̍��ڂ���Ƀn�C���C�g����A�L�[���g�p���ĊȒP�ɑI���ł�����@��񋟂��܂��B���X�g�̍��ڂ��N���b�N���đI�����邱�Ƃ��ł��A���͒l�������I�ɍX�V����ăh���b�v�_�E���������܂��B���ڂ��I�������ƁA`onItemSelected` �C�x���g���������܂��B�C�x���g���L�����Z�������ƍ��ڂ͑I�����ꂸ�Ƀh���b�v�_�E�������܂���B[**igxAutocomplete**]({environment:angularApiUrl}/classes/igxautocompletedirective.html) �f�B���N�e�B�u�͍��ڊԂ��ړ�����Ɠ����ɓ��͂���Ƀt�H�[�J�X����܂��B��҂ł͓��͂𑱍s�ł��܂��B`ESC` �L�[���g�p���ăh���b�v�_�E�� ���X�g����܂��B

[`igx-autocomplete`]({environment:angularApiUrl}/classes/igxautocompletedirective.html) �́A�g�p�\�ȃI�v�V�����̃v���o�C�_�[�Ƃ��� [`igx-drop-down`]({environment:angularApiUrl}/classes/igxdropdowncomponent.html) ���g�p���܂��B�܂�A�g�p�\�ȃO���[�v���A�e���v���[�g�A���ڂƃO���[�v�̖��������܂ރh���b�v�_�E���@�R���|�[�l���g�̋@�\���g�p����܂��B
</p>
<div class="divider"></div>

### �f��
�ȉ��̃T���v���́A`igx-input` �ɓK�p����� `igx-autocomplete` �f�B���N�e�B�u�̊ȒP�Ȏg�p���@�������܂��B�f�B���N�e�B�u�́A��`�����t�B���^�����O �p�C�v�̂��� `igx-drop-down` �ƂƂ��ɒ񋟂���܂��B 
<div class="sample-container loading" style="height: 400px;">
    <iframe id="autocomplete-sample" frameborder="0" seamless width="100%" height="100%" src="{environment:demosBaseUrl}/data-entries/autocomplete" onload="onSampleIframeContentLoaded(this);"></iframe>
</div>
<div>
    <button data-localize="stackblitz" disabled class="stackblitz-btn" data-iframe-id="autocomplete-sample" data-demos-base-url="{environment:demosBaseUrl}">view on stackblitz</button>
</div>
<div class="divider--half"></div>

> [!WARNING]
> Ignite UI for Angular �R���|�[�l���g���v���W�F�N�g�ɒǉ�����O�ɁA�K�v�Ȃ��ׂĂ̈ˑ��֌W���\�����A�v���W�F�N�g�̃Z�b�g�A�b�v�������������������Ƃ��m�F���Ă��������B�菇�́A[�͂��߂�](general/getting_started.md)�̃g�s�b�N�����m�F���������B

## �g�p���@
### �͂��߂�
[`igx-autocomplete`]({environment:angularApiUrl}/classes/igxautocompletedirective.html) ���g�p����ɂ́A**app.module** �� **IgxAutocompleteModule** �� **IgxDropDownModule** ���C���|�[�g����K�v������܂��B[`igx-autocomplete`]({environment:angularApiUrl}/classes/igxautocompletedirective.html) �� [igx-input]({environment:angularApiUrl}/classes/igxinputdirective.html) �ɓK�p�����ꍇ�́A**igxInputGroupModule** ���K�v�ƂȂ�܂��B

```typescript
// app.module.ts

...
import { 
    IgxAutocompleteModule,
    IgxDropDownModule, 
    IgxInputGroupModule 
} from 'igniteui-angular';

@NgModule({
    ...
    imports: [
        ..., 
        IgxAutocompleteModule,
        IgxDropDownModule,
        IgxInputGroupModule,
        ....
    ],
    ...
})
export class AppModule {}
```

�h���b�v�_�E���̎Q�ƂƂȂ� `igxAutocomplete` �f�B���N�e�B�u�ƒl��ǉ����܂��B

```html
<igx-input-group>
    <input igxInput name="towns" type="text"
        [igxAutocomplete]='townsPanel'/>
    <label igxLabel for="towns">Towns</label>
</igx-input-group>
<igx-drop-down #townsPanel>
    <igx-drop-down-item *ngFor="let town of towns">
        {{town}}
    </igx-drop-down-item>
</igx-drop-down>
```

```typescript
@Component({
    selector: 'app-autocomplete-sample',
    styleUrls: ['autocomplete.sample.css'],
    templateUrl: `autocomplete.sample.html`
})
export class AutocompleteSampleComponent {
    constructor() {
        this.towns = [ "New York", "Washington, D.C.", "London", "Berlin", "Sofia", "Rome", "Kiev",
            "Copenhagen", "Paris", "Barcelona", "Vienna", "Athens", "Dublin", "Yerevan",
            "Oslo", "Helsinki", "Stockholm", "Prague", "Istanbul", "El Paso", "Florence", "Moscow" ];
    }
}
```

### �L�[�{�[�h �i�r�Q�[�V����

 - �h���b�v�_�E�������Ă���ꍇ�A`Arrow Down`�A`Arrow Up`�A`Alt` + `Arrow Down`�A`Alt` + `Arrow Up` �̓h���b�v�_�E�����J���܂��B
 - �h���b�v�_�E�������Ă���ꍇ�A���̓t�B�[���h�ɓ��͂���ƃh���b�v�_�E�����J���܂��B
 - `Arrow Down` - �J���Ă���ꍇ�A���̃h���b�v�_�E�����ڂֈړ����܂��B
 - `Arrow Up` - �J���Ă���ꍇ�A�ȑO�̃h���b�v�_�E�����ڂֈړ����܂��B
 - `End` �͍Ō�̃h���b�v�_�E�����ڂֈړ����܂��B
 - `Home` �͍ŏ��̃h���b�v�_�E�����ڂֈړ����܂��B
 - `Enter` �́A���łɑI���������ڂ��m�肵�A�h���b�v�_�E������܂��B
 - `Esc` �̓h���b�v�_�E������܂��B

> ��: �I�[�g�R���v���[�g���J�����Ƃ��Ƀ��X�g�̍ŏ��̍��ڂ������I�ɑI������܂��B���X�g���t�B���^�[���ꂽ�Ƃ������l�ł��B

### �݊����T�|�[�g

`igxAutocomplete` �f�B���N�e�B�u��K�p����Ɨv�f���ȉ��� ARIA �����ő������܂��B
 - role="combobox" - �f�B���N�e�B�u���K�p�����v�f�̃��[���B
 - aria-autocomplete="list" - ���͊����̌�₪���X�g�̃t�H�[���ɓK�p���ꂽ���Ƃ������܂��B
 - aria-haspopup="listbox" �́A`igxAutocomplete` ���l���Ă���R���e�i���|�b�v�A�b�v�ł��邱�Ƃ��������߂̑����ł��B
 - aria-expanded="true"/"false" - �h���b�v�_�E���̏k����ԂɊ�Â����l�B
 - aria-owns="dropDownID" - �h���b�v�_�E���� id �͌���\�����邽�߂Ɏg�p����܂��B
 - aria-activedescendant="listItemId" - �l�����݂̃A�N�e�B�u���X�g�v�f�́@id �ɐݒ肳��܂��B

���Ɏg�p����� `drop-down` �R���|�[�l���g�́A�ȉ��� ARIA ���������J���܂��B 
 - role="listbox" - `igx-drop-down` �R���|�[�l���g �J�����_�[�ɓK�p����܂��B
 - role="group" -`igx-drop-down-item-group` �R���|�[�l���g �R���e�i�ɓK�p����܂��B
 - role="�I�v�V����" - `igx-drop-down` -item�R���|�[�l���g �R���e�i�ɓK�p����܂��B
 - `Igx-drop-down-item` �ɓK�p����� aria-disabled="true"/"false�v�A�����ȏꍇ�� `igx-drop-down-item-group` �R���|�[�l���g �R���e�i�B

### �I�[�g�R���v���[�g �h���b�v�_�E����L��/�����ɂ��܂��B

�ȉ��̃T���v���́A[`IgxAutocompleteDisabled`]({environment:angularApiUrl}/classes/igxautocompletedirective.html#disabled) ���`���A�I�[�g�R���v���[�g �h���b�v�_�E���̗L�����������������܂��B

```html
<igx-input-group>
    <input igxInput name="towns" type="text"
        [igxAutocomplete]='townsPanel'
        [igxAutocompleteDisabled]="disabled"/>
    <label igxLabel for="towns">Towns</label>
</igx-input-group>
<igx-drop-down #townsPanel>
    <igx-drop-down-item *ngFor="let town of towns">
        {{town}}
    </igx-drop-down-item>
</igx-drop-down>
<igx-switch name="toggle" [(ngModel)]="!disabled"></igx-switch>
```

```typescript
@Component({
    selector: 'app-autocomplete-sample',
    styleUrls: ['autocomplete.sample.css'],
    templateUrl: `autocomplete.sample.html`
})
export class AutocompleteSampleComponent {
    disabled;
    constructor() {
        this.towns = [ "New York", "Washington, D.C.", "London", "Berlin", "Sofia", "Rome", "Kiev",
            "Copenhagen", "Paris", "Barcelona", "Vienna", "Athens", "Dublin", "Yerevan",
            "Oslo", "Helsinki", "Stockholm", "Prague", "Istanbul", "El Paso", "Florence", "Moscow" ];
    }
}
```

### �h���b�v�_�E���̐ݒ�
`igx-autocomplete` �h���b�v�_�E���̔z�u�A�X�N���[�� �X�g���e�W�ƃA�E�g���b�g�́A[`IgxAutocompleteSettings`]({environment:angularApiUrl}/classes/igxautocompletedirective.html#autocompleteSettings) �I�v�V�������g�p���Đݒ�ł��܂��B�^�C�v [`AutocompleteOverlaySettings`]({environment:angularApiUrl}/classes/autocompleteoverlaysettings.html) ����̒l�������܂��B

�ȉ��̗�́A�f�B���N�e�B�u���K�p�������͂̏㕔�ɐݒ�\�ȃh���b�v�_�E���̈ʒu��\�����܂��B�X�ɊJ���A����̃A�j���[�V�����𖳌��ɂ��܂��B`ConnectedPositioningStrategy` ���g�p����܂��B

```html
<igx-input-group #inputGroup>
    <input igxInput name="towns" type="text"
        [igxAutocomplete]='townsPanel'
        [igxAutocompleteSettings]='settings'/>
    <label igxLabel for="towns">Towns</label>
</igx-input-group>
<igx-drop-down #townsPanel>
    <igx-drop-down-item *ngFor="let town of towns">
        {{town}}
    </igx-drop-down-item>
</igx-drop-down>
```

```typescript
@Component({
    selector: 'app-autocomplete-sample',
    styleUrls: ['autocomplete.sample.css'],
    templateUrl: `autocomplete.sample.html`
})
export class AutocompleteSampleComponent {
    constructor() {
        this.towns = [ "New York", "Washington, D.C.", "London", "Berlin", "Sofia", "Rome", "Kiev",
            "Copenhagen", "Paris", "Barcelona", "Vienna", "Athens", "Dublin", "Yerevan",
            "Oslo", "Helsinki", "Stockholm", "Prague", "Istanbul", "El Paso", "Florence", "Moscow" ];
    }
    @ViewChild('inputGroup', { read: IgxInputGroupComponent }) inputGroup: IgxInputGroupComponent;

    this.settings = {
        positionStrategy: new ConnectedPositioningStrategy({
            closeAnimation: null,
            openAnimation: null,
            verticalDirection: VerticalAlignment.Top,
            verticalStartPoint: VerticalAlignment.Top
        })
    };
}
```

> ��: �f�t�H���g�̔z�u�X�g���e�W�́A�󂫃X�y�[�X�Ɋ�Â��� `AutoPositionStrategy` �ƃh���b�v�_�E�����J���܂��B

## �A�v���P�[�V���� �V�i���I
### Reactive From ���ŃO���[�v������ igxAutocomplete 

�ȉ��̃T���v���́A�I�[�g�R���v���[�g�ŉf�悪 city �ŃO���[�v������Ă��� cinema �̑I�����\�ȃ��X�g�ł��B�C���v�b�g�̓��͂܂��� `Arrow Down` �L�[���g�p���ă��X�g���J���Acinema ��I�����܂��B���� movie �Ɠ��t��I�����܂��B

<div class="sample-container loading" style="height: 600px;">
    <iframe id="autocomplete-movie" frameborder="0" seamless width="100%" height="100%" src="{environment:demosBaseUrl}/data-entries/movie" onload="onSampleIframeContentLoaded(this);"></iframe>
</div>
<div>
    <button data-localize="stackblitz" disabled class="stackblitz-btn" data-iframe-id="autocomplete-movie" data-demos-base-url="{environment:demosBaseUrl}">view on stackblitz</button>
</div>

<div class="divider--half"></div>

��L�T���v���̂悤�ɃO���[�v�� `igxAutocomplete` ���g�p����ɂ́A�ȉ��̕��@�Ńf�[�^���`����K�v������܂��B

```html
<igx-input-group>
    <input igxInput #cinema name="cinema" formControlName="cinema" [igxAutocomplete]='cinemaPanel'/>
    <label igxLabel for="cinema">City & Cinema</label>
    <igx-suffix igxRipple><igx-icon fontSet="material">place</igx-icon> </igx-suffix>
</igx-input-group>
<igx-drop-down #cinemaPanel maxHeight="350px">
    <igx-drop-down-item-group *ngFor="let town of towns" [label]="town.name">
        <igx-drop-down-item *ngFor="let cinema of town.cinemas" [value]="cinema">
            {{cinema}}
        </igx-drop-down-item>
    </igx-drop-down-item-group>
</igx-drop-down>
```

### �I�[�g�R���v���[�g�������[�g�f�[�^�Ƀo�C���h
�ȉ��́A�����[�g�T�[�r�X�Ƀo�C���h���ꂽ�h���b�v�_�E���� `igxAutocomplete` �̃T���v���ł��B�ȉ��́A�Ƀf�[�^ ���[�h���ɒx��������ꍇ�A�h���b�v�_�E���̑���ɃJ�X�^�� �e���v���[�g��K�p�����T���v���ł��B

<div class="sample-container loading" style="height: 400px;">
    <iframe id="autocomplete-remote-sample" frameborder="0" seamless width="100%" height="100%" src="{environment:demosBaseUrl}/data-entries/autocomplete-remote" onload="onSampleIframeContentLoaded(this);"></iframe>
</div>
<div>
    <button data-localize="stackblitz" disabled class="stackblitz-btn" data-iframe-id="autocomplete-remote-sample" data-demos-base-url="{environment:demosBaseUrl}">view on stackblitz</button>
</div>
<div class="divider--half"></div>

## API
<div class="divider--half"></div>

* [IgxAutocompleteDirective]({environment:angularApiUrl}/classes/igxautocompletedirective.html)
* [IgxDropDownComponent]({environment:angularApiUrl}/classes/igxdropdowncomponent.html)
* [IgxInputGroup]({environment:angularApiUrl}/classes/igxinputgroupcomponent.html)

## ���m�̖��

### ���̑��̃��\�[�X
<div class="divider--half"></div>

* [IgxDropDownComponent](drop_down.md)
* [IgxInputGroup](input_group.md)
* [�e���v���[�g�쓮�t�H�[���̓���](input_group.md)
[Reactive Forms Integration](input_group_reactive_forms.md)

�R�~���j�e�B�ɎQ�����ĐV�����A�C�f�A������Ă��������B

* [Ignite UI for Angular** �t�H�[����** (�p��) ](https://www.infragistics.com/community/forums/f/ignite-ui-for-angular)
* [Ignite UI for Angular **GitHub** (�p��) ](https://github.com/IgniteUI/igniteui-angular)