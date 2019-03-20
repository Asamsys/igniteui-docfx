---
title: Doughnut Chart �R���|�[�l���g - �l�C�e�B�u Angular |Ignite UI for Angular
mentionedTypes: ['DoughnutChart', 'DoughnutChartType']
_description: Ignite UI for Angular Doughnut Chart �R���|�[�l���g�́A�����̕ϐ��𓯐S�~��̗ւŕ\���ł��A�f�[�^�͑��̃R���N�V�����⋤�ʃf�[�^�\�[�X�Ƀo�C���h�ł��܂��B
_keywords: Ignite UI for Angular, UI �R���g���[��, Angular �E�B�W�F�b�g, web �E�B�W�F�b�g, UI �E�B�W�F�b�g, Angular, �l�C�e�B�u Angular �R���|�[�l���g �X�C�[�g, �l�C�e�B�u Angular �R���g���[��, �l�C�e�B�u Angular �R���|�[�l���g Library, Angular Data Grid �R���|�[�l���g, Angular Data Grid �R���g���[��, Angular Doughnut Chart �R���g���[��, Angular Doughnut Chart �R���|�[�l���g, Angular data grid Doughnut Chart �R���|�[�l���g��, Angular Doughnut Chart

---

## �h�[�i�c �`���[�g

`IgxDoughnutChart` �R���|�[�l���g�͉~�`���[�g�Ɠ��l�A�ϐ��̔�������I�ɕ\�����܂��B�h�[�i�c�^�`���[�g �́A�����̕ϐ����R���Z���g���b�N �����O�ŕ\���ł��A�K�w�f�[�^�̉�����g�ݍ��݂ŃT�|�[�g���܂��B

### �f��

<div class="sample-container loading" style="height: 450px">
    <iframe id="doughnut-chart-overview-iframe" src='{environment:demosBaseUrl}/charts/doughnut-chart-overview' width="100%" height="100%" seamless="" frameBorder="0" onload="onSampleIframeContentLoaded(this);"></iframe>
</div>
<div>
    <button data-localize="stackblitz" class="stackblitz-btn"   data-iframe-id="doughnut-chart-overview-iframe" data-demos-base-url="{environment:demosBaseUrl}">StackBlitz �ŊJ��
    </button>
</div>

<div class="divider--half"></div>

### �ˑ��֌W

chart �p�b�P�[�W���C���X�g�[������Ƃ��� core �p�b�P�[�W���C���X�g�[������K�v������܂��B
**npm install igniteui-angular-core**
**npm install igniteui-angular-charts**

<!-- -->

���W�A�� �Q�[�W�� `NgModule` �Ƃ��ăG�N�X�|�[�g����邽�߁A�A�v���P�[�V������ `AppModule` �� `IgxDoughnutChart` ���C���|�[�g����K�v������܂��B

<!-- -->

```typescript
// app.module.ts
import { IgxDoughnutChartModule } from 'igniteui-angular-charts/ES5/igx-doughnut-chart-module';

@NgModule({
    imports: [
        // ...
        IgxDoughnutChartModule,
        // ...
    ]
})
export class AppModule {}
```

<div class="divider--half"></div>

### �g�p���@

�t�@�C�i�h�[�i�c�^ �`���[�g ���W���[�����C���|�[�g������A�`���[�g���f�[�^�Ƀo�C���h���܂��B
�R���|�[�l���g���쐬����ɂ́A�ŏ��Ƀo�C���h���邽�߂̃f�[�^���K�v�ɂȂ�܂��B�ȉ��̃R�[�h �X�j�y�b�g�́A�V���v���ȃf�[�^�\�[�X���쐬������@�������܂��B

```typescript
this.state = {
    data: [
        { MarketShare: 30, Company: "Google",    },
        { MarketShare: 15, Company: "Microsoft", },
        { MarketShare: 30, Company: "Apple",     },
        { MarketShare: 15, Company: "Samsung",   },
        { MarketShare: 10, Company: "Other",     },
] };
```

���̃R�[�h�́A�h�[�i�c�^�`���[�g����L�̃f�[�^�Ƀo�C���h������@�������Ă��܂��B

```html
 <igx-doughnut-chart width="700px"
                     height="500px">
    <igx-doughnut-chart-series>
        <igx-ring-series  [itemsSource]="data"
                labelMemberPath="Label"
                valueMemberPath="Value">
    </igx-doughnut-chart-series>
 </igx-doughnut-chart>
```

<div class="divider--half"></div>

## �\���\�ȗv�f

### �����̃����O

`IgxDoughnutChart` �́A�e�����O���قȂ�R���N�V�����Ƀo�C���h���ĕ����̃����O�𓯎��ɕ\���⋤�ʂ̃f�[�^�\�[�X�̋��L���ł��܂��B

### �X���C�X�̑I��

`IgxDoughnutChart` �R���|�[�l���g�́A1 �X���C�X�ȏ�̏�Ԃ�I���ς݂ɐݒ肷�邽�߂� API �����J���܂��B�C�ӂŁA�P��̃J�X�^�� �r�W���A�� �X�^�C����I���ς݃X���C�X�ɓK�p�ł��܂��B

**�X���C�X�I���̗L����/������** - `allowSliceSelection` ��ݒ肵�ăh�[�i�c�^�`���[�g�ŃX���C�X�̑I����L���܂��͖����ɂ��܂��B

**�I�����ꂽ�X���C�X�̃X�^�C���ݒ�** - �X���C�X�� `targetType` �őI�����ꂽ�X���C�X�̃X�^�C�����`���A�h�[�i�c�^�`���[�g�� `selectedStyle` �v���p�e�B�Ɋ��蓖�Ă邱�ƂŃX�^�C���ݒ�ł��܂��B

**�X���C�X���N���b�N���đI����Ԃ�ύX** - `sliceClick` �C�x���g�ɃC�x���g �n���h���[���A�^�b�`�����ꍇ�A�I����Ԃ�ύX���邽�߂̃C�x���g�����̃N���b�N�����X���C�X�ւ̎Q�Ƃ�񋟂��܂��B�h�[�i�c�^�`���[�g�́A�I�����ꂽ�X���C�X�̃X�^�C�������肷�� `selectedStyle` �v���p�e�B�����J���܂��B�f�t�H���g�ł́A�K�p�����X�^�C���͂���܂���B�X���C�X��I�����Ă��A���̌����ڂ͂ǂ̂悤�ɂ��ς��܂���B�Ǝ��̃X�^�C����I�����ꂽ�X���C�X�ɓK�p����ƁASlice �� `targetType` ������ Style ���`���āA`selectedStyle` �v���p�e�B�̒l�Ƃ��Đݒ肷��K�v������܂��B

**IsSelected �v���p�e�B�̐ݒ�** - `IgxDoughnutChart` �́A`isSelected` �v���p�e�B�𒼐ڕύX�ł��邷�ׂẴX���C�X�ւ̎Q�Ƃ�ێ����Ȃ��B�h�[�i�c�^�`���[�g�́A�X���C�X�̑I���ς�/�I�������̏�Ԃ̕ύX�Ɏg�p���� `sliceClick` �C�x���g�����J���܂��B

**SelectedSlices �R���N�V�����̃R���e���c��ύX** - `selectedSlices` �R���N�V�����̃R���e���c��ύX���đI�����ꂽ�X���C�X��ύX�ł��܂��B�h�[�i�c�^�`���[�g�́ASlice �I�u�W�F�N�g�ւɑ΂� `isSelected` �v���p�e�B�𒼐ڏC���ł��邷�ׂẴX���C�X�ւ̎Q�Ƃ�ێ����܂��B

### �X���C�X�I���̃f��

<div class="sample-container loading" style="height: 450px">
    <iframe id="doughnut-chart-selection-iframe" data-src='{environment:demosBaseUrl}/charts/doughnut-chart-selection' width="100%" height="100%" seamless="" frameborder="0" class="lazyload"></iframe>
</div>
<div>
    <button data-localize="stackblitz" class="stackblitz-btn"   data-iframe-id="doughnut-chart-selection-iframe" data-demos-base-url="{environment:demosBaseUrl}">StackBlitz �ŊJ��
    </button>
</div>

<div class="divider--half"></div>

### �X���C�X�̕���

`IgxDoughnutChart` �X���C�X�́A�v���O������ŁA�܂��̓��[�U�[ �C���^���N�V�����ɂ���ĕ����ł��܂��B

**�X���C�X�����̗L����/������**
`allowSliceExplosion` �v���p�e�B��ݒ肵�ăX���C�X�𕪊�����@�\��L���܂��͖����ɂł��܂��B

**�X���C�X�̃N���b�N���ɃX���C�X�̕�����Ԃ�ύX**
`sliceClick` �C�x���g�p�C�x���g �n���h���[���A�^�b�`����ƁA�C�x���g�����ŃN���b�N���ꂽ�X���C�X�ւ̎Q�Ƃ�񋟂���A������Ԃ��C���ł��܂��B

**IsExploded �v���p�e�B�̐ݒ�**
`IgxDoughnutChart` �́A`isExploded` �v���p�e�B�𒼐ڏC���ł��邷�ׂẴX���C�X�ւ̎Q�Ƃ�ێ����܂��B

**ExplodedSlices �R���N�V�����̃R���e���c�̏C��**
`explodedSlices` �R���N�V�����̃R���e���c��ύX���邱�Ƃɂ����J���ꂽ�X���C�X��ύX�ł��܂��B

### �X���C�X�̕����̃f��

<div class="sample-container loading" style="height: 450px">
    <iframe id="doughnut-chart-explosion-iframe" data-src='{environment:demosBaseUrl}/charts/doughnut-chart-explosion' width="100%" height="100%" seamless="" frameborder="0" class="lazyload"></iframe>
</div>
<div>
    <button data-localize="stackblitz" class="stackblitz-btn"   data-iframe-id="doughnut-chart-explosion-iframe" data-demos-base-url="{environment:demosBaseUrl}">StackBlitz �ŊJ��
    </button>
</div>

<div class="divider--half"></div>

### �}��

`IgxDoughnutChart` �͖}��̎g�p���T�|�[�g���Ă��܂��B�g�p�����}��́A��A�̃`���[�g����Đڑ�����Ă��� ItemLegend �ł��B

### �}��̃f��

<div class="sample-container loading" style="height: 450px">
    <iframe id="doughnut-chart-legend-iframe" data-src='{environment:demosBaseUrl}/charts/doughnut-chart-legend' width="100%" height="100%" seamless="" frameborder="0" class="lazyload"></iframe>
</div>
<div>
    <button data-localize="stackblitz" class="stackblitz-btn"   data-iframe-id="doughnut-chart-explosion-iframe" data-demos-base-url="{environment:demosBaseUrl}">StackBlitz �ŊJ��
    </button>
</div>
