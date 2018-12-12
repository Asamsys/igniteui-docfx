---
title: Doughnut Chart コンポーネント - Native Angular | Ignite UI for Angular
_description: Ignite UI for Angular Doughnut Chart コンポーネントは、複数の変数を同心円状の輪で表示でき、データは他のコレクションや共通データソースにバインドできます。 
_keywords: Ignite UI for Angular, UI controls, Angular widgets, web widgets, UI widgets, Angular, Native Angular Components Suite, Native Angular Controls, Native Angular Components Library, Angular Data Grid component, Angular Data Grid control, Angular Doughnut Chart Control, Angular Doughnut Chart Component, Angular data grid Doughnut Chart component example, Angular Doughnut Chart 
_language: ja
---
## ドーナツ型チャート

ドーナツ チャート コンポーネントは円チャートと同様、変数の発生を比例的に表示します。ドーナツ型チャート は、複数の変数をコンセントリック リングで表示でき、階層データの可視化を組み込みでサポートします。

### デモ

<div class="sample-container" style="height: 550px">
    <iframe id="doughnut-chart-overview-iframe" src='{environment:demosBaseUrl}/doughnut-chart-overview' width="100%" height="100%" seamless frameBorder="0" onload="onSampleIframeContentLoaded(this);"></iframe>
</div>
<div>
    <button data-localize="stackblitz" class="stackblitz-btn"   data-iframe-id="doughnut-chart-overview-iframe" data-demos-base-url="{environment:demosBaseUrl}">StackBlitz で表示
    </button>
</div>

<div class="divider--half"></div>

 ### 依存関係
chart パッケージをインストールするときに core パッケージもインストールする必要があります。

**npm install ignite-angular-charts ignite-angular-core**

ドーナツ型チャートが `NgModule` としてエクスポートされるため、アプリケーションで `AppModule` に _IgxDoughnutChartModule_ をインポートする必要があります。

```typescript
// app.module.ts
import { IgxDoughnutChartModule } from 'ignite-angular-charts/ES5/igx-doughnut-chart-module';

@NgModule({
    imports: [
        ...
        IgxDoughnutChartModule,
        ...
    ]
})
export class AppModule {}
```

<div class="divider--half"></div>

### 使用方法

ファイナドーナツ型 チャート モジュールをインポートした後、チャートをデータにバインドします。
Igx-doughnut-chart コンポーネントを作成するには、はじめにデータをバインドする必要があります。以下のコード スニペットは、シンプルなデータソースを作成する方法を示します。

```typescript
var data = [
 { "Label": "Item1", "Value": 5 },
 { "Label": "Item2", "Value": 6 },
 { "Label": "Item3", "Value": 3 },
 { "Label": "Item4", "Value": 7 },
 { "Label": "Item5", "Value": 4 }
];
```

以下のコードはドーナツ型チャートを上記のデータにバインドします。

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

## 構成可能な要素

### 複数のリング
xamDoughnutChart は、複数のリングを、異なるコレクションにバインド可能な各リングと同時に表示できます。または共通のデータ ソースを共有できます。

### スライスの選択

ドーナツ型チャート コンポーネントは、1 つ以上のスライスの状態を 選択された状態に設定する API を公開します。任意で、単一のカスタム ビジュアル スタイルを選択済みスライスに適用できます。

**スライス選択の有効化/無効化** - `allowSliceSelection` を設定してドーナツ型チャートでスライスの選択を有効または無効にします。  

**選択されたスライスのスタイル設定** - スライスの `targetType` で選択されたスライスのスタイルを定義し、ドーナツ型チャートの `selectedStyle` プロパティに割り当てることでスタイル設定できます。 
 
**スライスをクリックして選択状態を変更** - `sliceClick` イベントにイベント ハンドラーをアタッチした場合、選択状態を変更するためのイベント引数のクリックしたスライスへの参照を提供します。ドーナツ型チャートは、選択されたスライスのスタイルを決定する `selectedStyle` プロパティを公開します。デフォルトでは、適用されるスタイルはありません。スライスを選択しても、その見た目はどのようにも変わりません。選択されたスライスにカスタム スタイルを適用する場合は、Slice の `targetType` で Style を定義し、`selectedStyle` プロパティの値として設定する必要があります。 
 
**Setting the IsSelected property** - ドーナツ型チャートは、`isSelected` プロパティを直接変更できるすべてのスライスへの参照を保持しなす。ドーナツ型チャートは、スライスの選択済み/選択解除の状態の変更に使用する `sliceClick` イベントを公開します。  

 

### 

<div class="sample-container" style="height: 550px">
    <iframe id="doughnut-chart-selection-iframe" src='{environment:demosBaseUrl}/doughnut-chart-selection' width="100%" height="100%" seamless frameBorder="0" onload="onSampleIframeContentLoaded(this);"></iframe>
</div>
<div>
    <button data-localize="stackblitz" class="stackblitz-btn"   data-iframe-id="doughnut-chart-selection-iframe" data-demos-base-url="{environment:demosBaseUrl}">StackBlitz で表示
    </button>
</div>

<div class="divider--half"></div>


### スライスの分割





**スライスをクリックして展開状態を変更**
`sliceClick` イベントにイベント ハンドラーをアタッチした場合、クリックされたスライスへの参照がイベント引数に提供されて展開状態を変更できます。

**IsExploded プロパティの設定**
ドーナツ型チャートはすべてのスライスへの参照を保持して `isExploded` プロパティを直接変更できます。




### 

<div class="sample-container" style="height: 550px">
    <iframe id="doughnut-chart-explosion-iframe" src='{environment:demosBaseUrl}/doughnut-chart-explosion' width="100%" height="100%" seamless frameBorder="0" onload="onSampleIframeContentLoaded(this);"></iframe>
</div>
<div>
    <button data-localize="stackblitz" class="stackblitz-btn"   data-iframe-id="doughnut-chart-explosion-iframe" data-demos-base-url="{environment:demosBaseUrl}">StackBlitz で表示
    </button>
</div>

<div class="divider--half"></div>




