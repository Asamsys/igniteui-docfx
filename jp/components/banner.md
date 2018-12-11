---
title: Banner �R���|�[�l���g
_description: Ignite UI for Angular Banner �R���|�[�l���g�́A�ȒP�ɔ�N���^���b�Z�[�W���I�v�V��������Ɠ����ł��܂��B
_keywords: Ignite UI for Angular, UI �R���g���[��, Angular �E�B�W�F�b�g, web �E�B�W�F�b�g, UI �E�B�W�F�b�g, Angular, Native Angular �R���|�[�l���g �X�C�[�g, Native Angular �R���g���[��, Native Angular �R���|�[�l���g Library, Angular Banner �R���|�[�l���g, Angular Banner �R���g���[��
_language: ja
---
## Banner

<p class="highlight">
Ignite UI for Angular Banner �R���|�[�l���g�́A�X�i�b�N�o�[��蒷�����Ԃ̕\���Ń_�C�A���O���T���߂̃��b�Z�[�W���ȒP�ɕ\���ł��܂��BBanner �ɃJ�X�^�� �A�N�V���� �{�^����A�C�R���̕\����ݒ�ł��܂��B</p>
<div class="divider"></div>

### Banner �f��

<div class="sample-container loading" style="height: 400px">
    <iframe id="banner-sample-iframe" frameborder="0" seamless width="100%" height="100%" src="{environment:demosBaseUrl}/banner-sample-4" onload="onSampleIframeContentLoaded(this);"></iframe>
</div>
<div>
    <button data-localize="stackblitz" disabled class="stackblitz-btn" data-iframe-id="banner-sample-iframe" data-demos-base-url="{environment:demosBaseUrl}">stackblitz �ŕ\��</button>
</div>
<div class="divider--half"></div>

> [!NOTE]
> Ignite UI for Angular �R���|�[�l���g���v���W�F�N�g�ɒǉ�����O�ɁA�K�v�Ȃ��ׂĂ̈ˑ��֌W���\�����A�v���W�F�N�g�̃Z�b�g�A�b�v�������������������Ƃ��m�F���Ă��������B[�C���X�g�[��](https://www.infragistics.com/products/ignite-ui-angular/getting-started#installation)�̃g�s�b�N�Ŏ菇�����m�F���������B

## �g�p���@

Ignite UI for Angular Banner �̎g�p�́A�͂��߂� **app.module.ts** �t�@�C���� [`IgxBannerModule`]({environment:angularApiUrl}/classes/igxbannermodule.html) ���C���|�[�g���܂��B

```typescript
// app.module.ts

...
import { IgxBannerModule } from 'igniteui-angular';

@NgModule({
    ...
    imports: [..., IgxBannerModule],
    ...
})
export class AppModule {}
```
### �x�[�V�b�N Banner

Banner �R���|�[�l���g��\������ɂ́A({environment:angularApiUrl}/classes/igxbannercomponent.html#open) ���\�b�h���Ăяo���ă{�^���N���b�N�ŌĂяo���܂��BBanner ���b�Z�[�W���\������ɂ́ABanner �R���e���c���̃e�L�X�g��n���܂��B�w�肵�� Banner �̈�Ƀe�L�X�g���\������A�\������Banner�̓f�t�H���g �e���v���[�g���g�p���܂��B

```html
<!--banner.component.html-->

<igx-banner #connectionBanner>
    You are currently offline.
</igx-banner>
...
<button igxButton="raised" (click)="connectionBanner.toggle()">Toggle Banner</button>
```

Banner�́A�v�f���y�[�W �e���v���[�g�ɑ}�����ꂽ�ꏊ�ɂ��̑����ׂẴR���e���c���ړ����ĕ\������܂��BBanner�́A���邽�߂̍ŏ����̃��[�U�[���� (1-2 �N���b�N�Ȃ�) ��v�������N���^�R���e���c�\�����܂��B

#### �x�[�V�b�N Banner �f��

<div class="sample-container loading" style="height: 530px">
    <iframe id="banner-sample-1-iframe" frameborder="0" seamless width="100%" height="100%" src="{environment:demosBaseUrl}/banner-sample-1" onload="onSampleIframeContentLoaded(this);"></iframe>
</div>
<div>
    <button data-localize="stackblitz" disabled class="stackblitz-btn" data-iframe-id="banner-sample-1-iframe" data-demos-base-url="{environment:demosBaseUrl}">view on stackblitz</button>
</div>

### Banner �̃e���v���[�g��

[`IgxBannerComponent`]({environment:angularApiUrl}/classes/igxbannercomponent.html) �́A�}�e���A�� �f�U�C�� Banner �K�C�h���C���ɂł��邩���菀�����Ȃ���ȒP�ɃR���e���c���e���v���[�g�����܂��B

#### Banner ���b�Z�[�W�̕ύX

`igx-banner` �^�O�ɓn�����R���e���c��ύX����Banner�ɕ\������郁�b�Z�[�W��ύX�ł��܂��B�ȉ��́A�fConnection' Banner�̃R���e���c��ύX���Ă�葽���̏���񋟂��܂��B

```html
    <!--banner.component.html-->
    <igx-banner #connectionBanner>
        You have lost connection to the internet. This app is offline.
    </igx-banner>
    ...
    <button igxButton="raised" (click)="rateBanner.toggle()">Toggle Banner</button>
```

#### �A�C�R���̒ǉ�

Banner �R���e���c�� [`igx-icon`]({environment:angularApiUrl}/classes/igxiconmodule.html) ��n�����Ƃ��ł��A��� Banner ���b�Z�[�W�̍ŏ��ɔz�u����܂��B

> [!NOTE]
> ������ `igx-icon` �v�f�� Banner �̒��ڂ̎q���Ƃ��đ}�������ꍇ�ABanner �͂���炷�ׂĂ��ŏ��ɔz�u���悤�Ƃ��܂��B`igx-icon` �� 1 �̂݁A���ړn�����Ƃɒ��ӂ��Ă��������BBanner ���b�Z�[�W�̃A�C�R�����g�p����ꍇ�A`span` �^�O�Ń��b�v���Ă��������B

`Igx-icon` �� Banner �ɓn���ꍇ�A`igx-banner` �̃R���e���c�ɑ}�����Ă��������B

```html
    <!--banner.component.html-->
    <igx-banner #rateBanner>
        <igx-icon>signal_wifi_off</igx-icon>
        You have lost connection to the internet. This app is offline.
    </igx-banner>
    ...
```

#### �J�X�^�� Banner �{�^���̒ǉ�

[`IgxBannerModule`]({environment:angularApiUrl}/classes/igxbannermodule.html) �́ABanner �{�^�����e���v���[�g�����邽�߂̃f�B���N�e�B�u ([`IgxBannerActionsDirective`]({environment:angularApiUrl}/classes/igxbanneractionsdirective.html).) �����J���܂��B���̃f�B���N�e�B�u���g�p���ăf�t�H���g Banner �{�^�� (`Dismiss`) ���I�[�o�[���C�h���A���[�U�[��`�̃J�X�^�������ǉ����܂��B�قƂ�ǂ̃{�^�� �C���^���N�V������ Banner ����邱�Ƃł��邽�߁A`click` �n���h���[��Banner �� `close()` ���\�b�h���Ăяo���Ă��������B

> [!NOTE]
> Google �� [`�}�e���A�� �f�U�C��` �K�C�h���C��](https://material.io/design/components/banners.html#anatomy) �ł́ABanner �ɕ\������{�^���� 2 �܂łł��B`IgxBannerComponent` �́A`igx-banner-actions` �^�O�� 2 �v�f�ȏ�n�����Ƃ𖾎��I�ɐ���**���܂���**���A�}�e���A�� �f�U�C�� �K�C�h�ɏ]�����Ƃ𐄏����܂��B 

Connection Banner �̃e���v���[�g���́A`igx-banner-actions` �Z���N�^�[���g�p����J�X�^�� �A�N�V���� �n���h���[��n�����Ƃ��ł��܂��B

```html
    <!--banner.component.html-->
    <igx-banner #rateBanner>
        <igx-icon>signal_wifi_off</igx-icon>
        You have lost connection to the internet. This app is offline.
        <igx-banner-actions>
            <button igxButton igxRipple (click)="connectionBanner.close()">Continue Offline</button>
            <button igxButton igxRipple (click)="wifiState = true">Turn On Wifi</button>
        </igx-banner-actions>
    </igx-banner>
    ...
```
����I�v�V���� (`'Continue Offline'`) �͏ڍׂȃ��W�b�N��K�v�Ƃ��Ȃ����߁A`connectionBanner.close()` �݂̂̌Ăяo�����\�ł��B�m�F���� (`�eTurn On Wifi�f`) �͒ǉ��̃��W�b�N��K�v�Ƃ��邽�߁A�R���|�[�l���g�Œ�`���܂��B

```typescript
// banner.component.ts
import { Component, OnInit, OnDestroy, ViewChild } from "@angular/core";
import { IgxBannerComponent } from 'igniteui-angular'
...
export class MyBannerComponent implements OnInit, OnDestroy {
    @ViewChild(IgxBannerComponent) public banner: IgxBannerComponent;
    public onNetworkStateChange = new Subject(); // Emits when WiFi state is changed
    private _wifiState = false;
    public get wifiState(): boolean {
        return this._wifiState;
    }
    public set wifiState(v: boolean) {
        this._wifiState = v;
        this.onNetworkStateChange.next();
    }
    ...
    public ngOnInit() { // subscribe to the event;
        this.banner.open();
        this.onNetworkStateChange.subscribe(() => this.refreshBanner()); // call change handler
    }

    public ngOnDestroy(): void { // unsubscribe
        this.onNetworkStateChange.complete();
    }
    ...
    // Define change handler
    public refreshBanner() {
        if (!this.wifiState) {
            this.banner.open();
        } else {
            if (!this.banner.collapsed) {
                this.banner.close();
            }
        }
    }
}
```
��L�̃R�[�h �X�j�y�b�g�̐����B
 - `onNetworkStateChange` �̎��� - �ύX�����b�X������ `Observable`�B
 - `ngOnInit` �̐V���� Observable �ɃT�u�X�N���C�u���܂��B`Observable` ���������邲�ƂɃ��\�b�h���Ăяo���܂��B
 - `ngOnDestroy` �� Observable �� `complete` ���\�b�h���Ăяo���ă��������[�N��h�~���܂��B
 - `refreshBanner` �̃{�f�B���` - WiFi ��ԂɊ�Â���Banner�� `show()` �܂��� `close()` ���܂��B

#### �f���̃e���v���[�g��

<div class="sample-container loading" style="height: 530px">
    <iframe id="banner-sample-2-iframe" frameborder="0" seamless width="100%" height="100%" src="{environment:demosBaseUrl}/banner-sample-2" onload="onSampleIframeContentLoaded(this);"></iframe>
</div>
<div>
    <button data-localize="stackblitz" disabled class="stackblitz-btn" data-iframe-id="banner-sample-2-iframe" data-demos-base-url="{environment:demosBaseUrl}">stackblitz �ŕ\��</button>
</div>

### �J�X�^�� �A�j���[�V�����̓K�p

Banner �R���|�[�l���g�́A[`animationSettings`]({environment:angularApiUrl}/classes/igxbannermodule.html#animationsettings) �ɃJ�X�^�� �I�[�v���̐ݒ�ƃA�j���[�V�����̃N���[�Y�����e���� `Input` �v���p�e�B�����J���܂��B�J�X�^�� �A�j���[�V�����́A���[�U�[��`�܂��� [`IgniteUI for Angular animation suite`]({environment:sassApiUrl}/index.html) ����n�����Ƃ��ł��܂��BBanner�Ŏg�p�����f�t�H���g �A�j���[�V�����́A`growVerIn` ���J�n�A`growVerOut` ���I���ł��B

�X���C�h�C�����邽�߂�Banner���g�p����A�j���[�V������ύX���܂��B

```html
<!--banner.component.html-->
    <igx-banner #connectionBanner [animationSettings]="animationSettings">
        ...
    </igx-banner>
    ...
```

```typescript
// banner.component.ts
import { IgxBannerComponent, slideInLeft, slideOutRight } from 'igniteui-angular'
...
export class MyBannerComponent {
    ...
    public animationSettings = {
        openAnimation: slideInLeft,
        closeAnimation: slideOutRight
    }
    ...
}
```

#### �A�j���[�V���� �f��

<div class="sample-container loading" style="height: 530px">
    <iframe id="banner-sample-3-iframe" frameborder="0" seamless width="100%" height="100%" src="{environment:demosBaseUrl}/banner-sample-3" onload="onSampleIframeContentLoaded(this);"></iframe>
</div>
<div>
    <button data-localize="stackblitz" disabled class="stackblitz-btn" data-iframe-id="banner-sample-3-iframe" data-demos-base-url="{environment:demosBaseUrl}">view on stackblitz</button>
</div>

### �C�x���g�Ƀo�C���h
Banner �R���|�[�l���g�͏�Ԃ̕ύX���ɃC�x���g�𔭐����܂��B[`onOpening`]({environment:angularApiUrl}/classes/igxbannercomponent.html#onopening) �� [`onOpened`]({environment:angularApiUrl}/classes/igxbannercomponent.html#onopened) �� Banner ���\������� (�O�ƌ��) �Ƃ��ɌĂяo����܂��B����A[`onClosing`]({environment:angularApiUrl}/classes/igxbannercomponent.html#onclosing) �� [`onClosed`]({environment:angularApiUrl}/classes/igxbannercomponent.html#onclosed) ��Banner������Ƃ��ɃG�~�b�g����܂��B*Ing* �C�x���g (`onOpening`, `onClosing`) �̓L�����Z���\�ł��B `ICancelEventArgs` �C���^�[�t�F�C�X���g�p���ăI�u�W�F�N�g�� `cancel` �v���p�e�B�������܂��B`cancel` �v���p�e�B�� true �ɐݒ肵�܂��B�Ή�����G���h����ƃC�x���g�̓g���K�[����܂���B���Ƃ��΁A`onOpening` ���L�����Z�������ꍇ�ABanner �� `open` ���\�b�h�͊��������� Banner ���\������܂���B

���������I�u�W�F�N�g�փo�C���h�����C�x���g���L�����Z�����邽�߂� `cancel` �v���p�e�B�� `true` �ɐݒ肵�܂��B

```html
<!--banner.component.html-->
    <igx-banner #connectionBanner (onOpening)="handleOpen($event)">
        ...
    </igx-banner>
```
```typescript
// banner.component.ts
...
export class MyBannerComponent {
    ...
    public handleOpen(event) {
        event.cancel = true;
    }
}
```
> [!NOTE]
> ��L���K�p�����ƃI�[�v�j���O �C�x���g����ɃL�����Z������邽�߁ABanner ���J�����Ƃ͂���܂���B

## API ���t�@�����X

* [`IgxBannerComponent API`]({environment:angularApiUrl}/classes/igxbannercomponent.html)
* [`IgxBannerModule`]({environment:angularApiUrl}/classes/igxbannermodule.html)
* [`IgxBanner Styles`]({environment:sassApiUrl}/index.html#mixin-igx-banner)