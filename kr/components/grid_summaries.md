﻿---
title: 요약 컴포넌트- 네이티브 Angular | Ignite UI for Angular
_description: Ignite UI for Angular 요약 컴포넌트는 열의 데이터 유형에 따라 사전 정의된 기본 요약 항목 세트를 가진 별도의 컨테이너에서 열 정보를 표시할 수 있습니다.
_keywords: Ignite UI for Angular, UI 컨트롤, Angular 위젯, 웹 위젯, UI 위젯, Angular, 네이티브 Angular 컴포넌트 세트, 네이티브 Angular 컨트롤, 네이티브 Angular 컴포넌트 라이브러리, 네이티브 Angular 컴포넌트, Angular 그리드, Angular 데이터 그리드 컴포넌트, Angular 데이터 그리드 컨트롤, Angular 그리드 컴포넌트, Angular 그리드 컨트롤, Angular 고성능 그리드, 요약, 개요
_language: kr
---

### 그리드 요약

Ignite UI for Angular 그리드 컴포넌트에는 열 단위 수준에서 작동하는 **summaries** 기능이 있습니다.

#### 데모

<div class="sample-container loading" style="height:650px">
    <iframe id="grid-summary-sample-iframe" src='{environment:demosBaseUrl}/grid-summary' width="100%" height="100%" seamless frameBorder="0" onload="onSampleIframeContentLoaded(this);"></iframe>
</div>
<br/>
<div>
<button data-localize="stackblitz" disabled class="stackblitz-btn" data-iframe-id="grid-summary-sample-iframe" data-demos-base-url="{environment:demosBaseUrl}">view on stackblitz</button>
</div>
<div class="divider--half"></div>

> [!NOTE]
> 열 요약은 **모든 열 값의 함수**이지만 필터링이 적용된 경우에는 열 요약은 **필터링된 결과 값의 함수**가 됩니다

사용자는 열의 데이터 유형에 따라 사전 정의된 기본 요약 항목 세트를 가진 별도의 컨테이너에서 열 정보를 표시할 수 있습니다. Ignite UI for Angular에서 **Grid summaries**을 열 단위 수준으로 활성화하고 필요한 열에 대해서만 활성화할 수 있습니다. 그리드 요약은 열의 데이터 유형에 따라 사전 정의된 기본 요약 세트를 제공하므로 시간을 절약할 수 있습니다.


`string` 및 `boolean` 데이터 유형의 경우 다음의 함수를 사용할 수 있습니다:
 - count

`number` 데이터 유형의 경우 다음의 함수를 사용할 수 있습니다:
 - count
 - min
 - max
 - average
 - sum

`date` 데이터 유형의 경우 다음의 함수를 사용할 수 있습니다:
 - count
 - earliest
 - latest

**열 요약**은 `hasSummary` 속성을 `true`로 설정하여 열 단위로 활성화됩니다. 또한, 각 열의 요약은 열 데이터 형식에 따라 해결되는 것에 유의하십시오. `igx-grid` 에서 기본 열 데이터 유형은 `string`이므로 `number` 또는 `date`별 요약을 원하는 경우 `dataType` 속성을 `number` 또는 `date`로 설정해야 합니다.

```html
<igx-grid #grid1 [data]="data" [autoGenerate]="false" height="800px" width="800px" (onColumnInit)="initColunm($event)" >
    <igx-column field="ProductID" header="Product ID" width="200px"  [sortable]="true">
    </igx-column>
    <igx-column field="ProductName" header="Product Name" width="200px" [sortable]="true" [hasSummary]="true">
    </igx-column>
    <igx-column field="ReorderLevel" width="200px" [editable]="true" [dataType]="'number'" [hasSummary]="true">
    </igx-column>
</igx-grid>
```

특정 열 또는 열 목록에서 요약을 활성화/비활성화하는 또 다른 방법은 **igx-grid**의 공개 메소드 `enableSummaries`/`disableSummaries`를 사용하는 것입니다.

```html
<igx-grid #grid1 [data]="data" [autoGenerate]="false" height="800px" width="800px" (onColumnInit)="initColunm($event)" >
    <igx-column field="ProductID" header="Product ID" width="200px"  [sortable]="true">
    </igx-column>
    <igx-column field="ProductName" header="Product Name" width="200px" [sortable]="true" [hasSummary]="true">
    </igx-column>
    <igx-column field="ReorderLevel" width="200px" [editable]="true" [dataType]="'number'" [hasSummary]="false">
    </igx-column>
</igx-grid>
<button (click)="enableSummary()">Enable Summary</button>
<button (click)="disableSummary()">Disable Summary </button>
```
```typescript
public enableSummary() {
    this.grid1.enableSummaries([{fieldName: "ReorderLevel", customSummary: this.mySummary},
    {fieldName: "ProductID"}]);
  }
public disableSummary() {
    this.grid1.disableSummaries("ProductName");
}
```

참고: `hasSummary` 속성을 `false`에서 `true`로 또는 그 반대로 변경하여 특정 열 요약을 런타임으로 활성화 또는 비활성화하는 옵션이 있지만 `recalculateSummaries()` 메소드를 명시적으로 호출해야 합니다.

```html
<igx-grid #grid1 [data]="data" [autoGenerate]="false" height="800px" width="800px" (onColumnInit)="initColunm($event)" >
    <igx-column field="ProductID" header="Product ID" width="200px"  [sortable]="true">
    </igx-column>
    <igx-column field="ProductName" header="Product Name" width="200px" [sortable]="true" [hasSummary]="true">
    </igx-column>
    <igx-column field="ReorderLevel" width="200px" [editable]="true" [dataType]="'number'" [hasSummary]="false">
    </igx-column>
</igx-grid>
<button (click)="toggleSummary()">Enable Summary</button>
```

```typescript
...
    public toggleSummary() {
        this.grid1.getColumnByName('ReorderLevel').hasSummary = true;
        this.grid1.recalculateSummaries();
    }
...

```
이러한 함수가 요구 사항을 충족시키지 못하면 특정 열에 대한 사용자 요약을 제공할 수 있습니다. 이를 실행하려면 열 데이터 유형 및 필요에 따라 기본 클래스인 `IgxSummaryOperand`, `IgxNumberSummaryOperand` 또는 `IgxDateSummaryOperand` 중에서 하나를 무효화해야 합니다. 이 방법으로 기존 함수를 다시 정의하거나 새로운 함수를 추가할 수 있습니다. `IgxSummaryOperand` 클래스는 `count` 메소드에 대해서만 기본 실행을 제공합니다. `IgxNumberSummaryOperand`는 `IgxSummaryOperand`를 확장하고 `min`, `max`, `sum` 및 `average`의 구현을 제공합니다. `IgxDateSummaryOperand`는 `IgxSummaryOperand`를 확장하며 `earliest` 및 `latest`를 제공합니다.

```typescript
import { IgxSummaryResult, IgxSummaryOperand, IgxNumberSummaryOperand, IgxDateSummaryOperand } from 'igniteui-angular/grid/grid-summary';

class MySummary extends IgxNumberSummaryOperand {

  constructor() {
    super();
  }
  operate(data?: any[]): IgxSummaryResult[] {
    const result = super.operate(data);
    result.push({
      key: 'test',
      label: 'Test',
      summaryResult: data.filter(rec => rec > 10 && rec < 30).length
    });

    return result;
  }
}
```

아래의 코드에서 메소드 **operate**은 인터페이스인 **IgxSummaryResult**의 목록을 반환하는 것을 볼 수 있습니다.
```typescript
interface IgxSummaryResult {
    key: string;
    label: string;
    summaryResult: any;
}
```
이제 `UnitsInStock` 열에 사용자 요약을 추가해 보겠습니다. `summaries` 속성을 아래에서 작성하는 클래스로 설정하면 됩니다.
```html
<igx-grid #grid1 [data]="data" [autoGenerate]="false" height="800px" width="800px" (onColumnInit)="initColunm($event)" >
    <igx-column field="ProductID" width="200px"  [sortable]="true">
    </igx-column>
    <igx-column field="ProductName" width="200px" [sortable]="true" [hasSummary]="true">
    </igx-column>
    <igx-column field="UnitsInStock" width="200px" [dataType]="'number'" [hasSummary]="true" [summaries]="mySummary" [sortable]="true">
    </igx-column>
    <igx-column field="ReorderLevel" width="200px" [editable]="true" [dataType]="'number'" [hasSummary]="true">
    </igx-column>
</igx-grid>
```

```typescript
...
export class GridComponent implements OnInit {

  mySummary = MySummary;

    ....
}
```

퍼포먼스를 향상 시키기 위해 **igx-grid**는 모든 요약을 캐시하고, 데이터를 통해 CRUD 조작을 실행하는 경우에 다시 계산합니다. 그러나, 데이터 소스가 **igx-grid** 이외로 변경되는 경우,  `clearSummaryCache()` 메소드를 호출하여 **igx-grid**의 요약을 다시 계산하도록 명시적으로 설정해야 합니다.

```html
<igx-grid #grid1 [data]="data" [autoGenerate]="false" height="800px" width="800px" (onColumnInit)="initColunm($event)" >
    <igx-column field="ProductID" width="200px"  [sortable]="true">
    </igx-column>
    <igx-column field="ProductName" width="200px" [sortable]="true" [hasSummary]="true">
    </igx-column>
    <igx-column field="UnitsInStock" width="200px" [dataType]="'number'" [hasSummary]="true" [summaries]="mySummary" [sortable]="true">
    </igx-column>
    <igx-column field="ReorderLevel" width="200px" [editable]="true" [dataType]="'number'" [hasSummary]="true">
    </igx-column>
</igx-grid>
<button (click)="updateData()">Update Data</button>
```

```typescript
...
export class GridComponent implements OnInit {

 updateData() {
    const d = [].concat(this.data).concat(this.data.slice(0, 15));
    this.data = d;
    this.grid1.clearSummaryCache();
  }
}
```

`http` 요청이 실행된 경우에도 동일하게 적용되므로 캐시를 갱신해야 합니다.

```typescript
this.http.get<any[]>('/assets/data.json')
    .subscribe(data => {
    this.data = data;
    this.grid1.clearSummaryCache();
});
```

### 추가 리소스
<div class="divider--half"></div>

* [그리드 개요](grid.md)
* [가상화 및 성능](grid_virtualization.md)
* [페이징](grid_paging.md)
* [필터링](grid_filtering.md)
* [정렬](grid_sorting.md)
* [열 이동](grid_column_moving.md)
* [열 핀 고정](grid_column_pinning.md)
* [열 크기 조정](grid_column_resizing.md)
* [선택](grid_selection.md)

<div class="divider--half"></div>
커뮤니티는 활동적이고 새로운 아이디어를 항상 환영합니다.

* [Ignite UI for Angular **Forums**](https://www.infragistics.com/community/forums/f/ignite-ui-for-angular)
* [Ignite UI for Angular **GitHub**](https://github.com/IgniteUI/igniteui-angular)