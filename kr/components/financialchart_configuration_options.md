﻿---
title: 금융 차트 - 컨피규레이터 옵션
_description: Ignite UI for Angular 금융 차트 컴포넌트는 간단하고 직관적인 API를 사용하여 재무 데이터를 표시하도록 쉽게 구성되어 있으며, 사용자가 데이터를 바인딩하면 차트는 데이터를 시각화하고 해석할 수 있는 다양한 방법을 제공합니다.
_keywords: Ignite UI for Angular, Angular, 네이티브 Angular 컴포넌트 세트, 네이티브 Angular 컨트롤, 네이티브 Angular 컴포넌트, 네이티브 Angular 컴포넌트 라이브러리, Angular 차트, Angular 차트 컨트롤, Angular 차트 예제, Angular 그리드 컴포넌트, Angular 차트 컴포넌트, Angular 금융 차트
_language: kr
---
## 컨피규레이터 옵션

`igx-financial-chart` 컨트롤은 탐색 동작, 추세선 레이어, 오버레이, 차트 제목, 부제 등의 사용자 지정이 가능한 많은 비주얼을 제공합니다.

### 데모

<div class="sample-container" style="height: 550px">
    <iframe id="financial-chart-trendlines-iframe" src='{environment:demosBaseUrl}/financial-chart-trendlines' width="100%" height="100%" seamless frameBorder="0" onload="onSampleIframeContentLoaded(this);"></iframe>
</div>
<div>
    <button data-localize="stackblitz" disabled class="stackblitz-btn"   data-iframe-id="financial-chart-trendlines-iframe" data-demos-base-url="{environment:demosBaseUrl}">View on StackBlitz
    </button>
</div>

<div class="divider--half"></div>

### 탐색 구성
`igx-financial-chart` 컨트롤에서 차트 탐색은 기본적으로 사용할 수 있습니다. 그러나, 다음 속성을 설정하여 사용자 정의를 실시할 수 있습니다:

- `isHorizontalZoomEnabled` - 차트가 사용자 조작에 의해 수평 방향으로 줌이 가능한지 여부를 지정합니다. 기본적으로 이 속성은 true로 설정됩니다.
- `isVerticalZoomEnabled` - 차트가 사용자 조작에 의해 수직 방향으로 줌이 가능한지 여부를 지정합니다. 기본적으로 이 속성은 false로 설정됩니다.
- `isWindowSyncedToVisibleRange` - true로 설정하면 Y축의 표시 데이터 범위가 자동으로 조정됩니다. 기본적으로 이 속성은 false로 설정됩니다.
- `windowRect` - igxFinancialChart의 스크롤 상태 및 줌 상태를 검색하거나 지정하는데 사용할 수 있습니다. `windowRect`는 좌표 및 크기가 0~1 사이인 직사각형으로 표현됩니다.

```html
 <igx-financial-chart
    [dataSource]="data"
    width="850px"
    height="600px"
    isHorizontalZoomEnabled="true"
    isVerticalZoomEnabled="false">
 </igx-financial-chart>
```

### 가격 창 구성
가격 창은 항상 금융 차트에 표시되며 차트 유형을 변경하고 비주얼 모양을 사용자 정의하여 구성할 수 있습니다. 다음의 코드는 가격 창에서 시리즈의 브러시 및 두께를 설정하는 방법을 보여줍니다.

```html
 <igx-financial-chart
    [dataSource]="data"
    width="850px"
    height="600px"
    chartType="Candle"
    brushes="Green, Blue"
    outlines="Green, Blue"
    negativeBrushes="Red"
    negativeOutlines="Red"
    thickness="2">
 </igx-financial-chart>
```

### 오버레이 구성
기본적으로 오버레이는 igxFinancialChart에 표시되지 않습니다. `BollingerBands` 및 `PriceChannel`의 두 가지 유형의 오버레이가 있습니다. 오버레이의 기본 설정을 사용자 정의할 수도 있습니다. 다음의 코드는 색상, 오버레이의 외곽선 및 두께를 설정하는 방법을 보여줍니다.

```html
 <igx-financial-chart
    [dataSource]="data"
    width="850px"
    height="600px"
    overlayTypes="BollingerBands"
    overlayBrushes="Red"
    overlayOutlines="Green"
    overlayThickness="2">
 </igx-financial-chart>
```

### 인디케이터 구성
기본적으로 인디케이터 창은 금융 차트에 표시되지 않습니다. 도구 모음을 사용하면 최종 사용자가 런타임 시 표시할 인디케이터를 선택할 수 있습니다. 창을 표시하려면 다음의 코드와 같이 인디케이터 유형을 설정해야 합니다.

```html
 <igx-financial-chart
    [dataSource]="data"
    width="850px"
    height="600px"
    indicatorTypes="AverageTrueRange,ForceIndex"
    indicatorBrushes="Green, Blue"
    indicatorNegativeBrushes="Red"
    indicatorDisplayTypes="Line"
    indicatorThickness="2">
 </igx-financial-chart>
```

### 볼륨 창 구성
기본적으로 볼륨 창은 금융 차트에 표시되지 않습니다. 그러나, 차트 도구 모음을 사용하여 런타임에 이 창을 사용하거나 다음의 코드와 같이 프로그래밍 방식으로 사용할 수 있습니다.

```html
 <igx-financial-chart
    [dataSource]="data"
    width="850px"
    height="600px"
    volumeType="Column"
    volumeBrushes="Green, Blue"
    volumeOutlines="White"
    volumeThickness="2">
 </igx-financial-chart>
```

### 추세선 구성
기본적으로 추세선은 igxFinancialChart에 표시되지 않습니다. 추세선이 표시되는 경우 모든 차트 창에 동일한 추세선이 표시됩니다. 추세선의 기본 설정을 사용자 정의할 수도 있습니다.

다음의 코드는 추세선의 색상 및 두께를 설정하는 방법을 보여줍니다.

```html
 <igx-financial-chart
    [dataSource]="data"
    width="850px"
    height="600px"
    trendLineType="QuinticFit"
    trendLineThickness="2"
    trendLineBrushes="Green, Blue">
 </igx-financial-chart>
```

### 제목 구성
차트 도구 모음 및 금융 차트의 가격 창 사이에 표시될 제목과 부제를 설정할 수 있습니다. 다음의 코드는 제목 및 부제를 설정하는 방법을 보여줍니다.

```html
 <igx-financial-chart
    [dataSource]="data"
    width="850px"
    height="600px"
    chartTitle="Stock Prices"
    subtitle="Between 2000 and 2015">
 </igx-financial-chart>
```