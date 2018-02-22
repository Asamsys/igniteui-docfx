---
title: igxFor
_description: Ignite UI for Angular now exposes a virtual igxFor directive similar to ngFor, which virtualizes DOM object rendering by visualizing only the visible chunks of the data in the DOM.
_keywords: Ignite UI for Angular, UI controls, Angular widgets, web widgets, UI widgets, Angular, Native Angular Components Suite, Native Angular Controls, Native Angular Components Library, Virtualization, Performance, Virtual directive, Virtual For
---

## igxFor

<p class="highlight">
`igxForOf` is now available as an alternative to `ngForOf` for templating large amounts of data. The `igxForOf` uses virtualization technology behind the scenes to optimize DOM rendering and memory consumption. Virtualization technology works similar to Paging by slicing the data into smaller chucks which are swapped from a container viewport while the user scrolls the data horizontally/vertically. The difference with the Paging is that virtualization mimics the natural behavior of the scrollbar.
The directive is creating scrollable containers and renders small chunks of the data. Is is used inside `igx-grid` and it can be used to build virtual `igx-list`.
</p>

### igxFor Demo

<div class="sample-container loading" style="height:780px">
    <iframe src='{environment:demosBaseUrl}/igx-for-sample-1' width="100%" height="100%" seamless frameBorder="0" onload="onSampleIframeContentLoaded(this);"></iframe>
</div>
<br/>
<!--<button data-localize="stackblitz" class="stackblitz-btn">view on stackblitz</button> -->

### Dependencies

The `igxFor` directive is exported as as an `NgModule`, thus all you need to do in your application is to import the _IgxForOfModule_
inside your `AppModule`:

```typescript
// app.module.ts

import { IgxForOfModule } from 'igniteui-angular/main';

@NgModule({
    imports: [
        ...
        IgxForOfModule,
        ...
    ]
})
export class AppModule {}
```

### Usage

Now that we have the `igxForOf` module imported, let’s get started with a basic configuration of the **igxFor** that binds to local data:

```html
<span #container>
    <ng-template *igxFor="data"></ng-template>
</span>
```



The **data** property is an array that provides the virtualized data.


The directive can be used to virtualize the data in vertical, horizontal or both directions.
### Vertical virtualization

```html
<table style='height:500px;'>
    <ng-template igxFor let-item [igxForOf]="data" #virtDirVertical
        [igxForScrollOrientation]="'vertical'"
        [igxForContainerSize]='"500px"'
        [igxForItemSize]='"50px"'
        let-rowIndex="index">
            <tr style='height:50px;'>{{rowIndex}} : {{item.text}}</tr>
    </ng-template>
</table>
```

### Horizontal virtualization

```html
<table> 
    <tbody style='display:grid;'>
    <tr style='width:500px; height:118px;'>               
        <ng-template igxFor let-item [igxForOf]="data" #virtDirHorizontal
            [igxForScrollOrientation]="'horizontal'"
            [igxForContainerSize]='"500px"'
            let-rowIndex="index">
                <td  [style.width.px]='item.width' style='height:100px;'>{{rowIndex}} : {{item.text}}</td>
            </ng-template>
    </tr>
    </tbody>
</table>
```

### Horizontal and vertical virtualization

```html
<table #container [style.width]='width' [style.height]='height'>
    <ng-template #scrollContainer igxFor let-rowData [igxForOf]="data"
        [igxForScrollOrientation]="'vertical'"
        [igxForContainerSize]='height'
        [igxForItemSize]='"50px"'>
        <tr [style.display]="'flex'" [style.height]="'50px'">
            <ng-template #childContainer igxFor let-col [igxForOf]="cols"
                [igxForScrollOrientation]="'horizontal'"
                [igxForScrollContainer]="parentVirtDir"
                [igxForContainerSize]='width'>
                    <td [style.min-width]='col.width + "px"'>{{rowData[col.field]}}</td>
            </ng-template>
        </tr>
    </ng-template>
</table>
```
### igxFor bound to remote service

The `igxForOf` directive can be bound to remote service. You need to use `Observeble` property - `remoteData`(in the following case). Also the `chunkLoading` event should be utilized to trigger the requests to the data.

```html
<div style='height:500px;'>
    <ng-template igxFor let-item [igxForOf]="remoteData | async" (onChunkPreload)="chunkLoading($event)"
    [igxForScrollOrientation]="'vertical'"
    [igxForContainerSize]='"500px"'
    [igxForItemSize]='"50px"'
    [igxForRemote]='true'
    let-rowIndex="index" #virtDirRemote>
    <div style='height:50px;'>{{item.ProductID}} : {{item.ProductName}}</div>
    </ng-template>
</div>
```

Also there is a requirement to set the `totatItemsCount` property in the instance of `igxForOf`.
```typescript
this.virtDirRemote.totalItemCount = data["@odata.count"];
```

In order access the directive instance from the component it should be marked as `ViewChild`:
```typescript
@ViewChild("virtDirRemote", { read: IgxForOfDirective })
public virtDirRemote: IgxForOfDirective<any>;
```
And after the request to load the first chunk, the `totalItemCount` can be set:
```typescript
public ngAfterViewInit() {
    this.remoteService.getData(this.virtDirRemote.state, (data) => {
        this.virtDirRemote.totalItemCount = data["@odata.count"];
    });
}
```
When requesting data you can take advantage of `IgxForOfState` interface, which provides the `startIndex` and `chunkSize`. But note, that initialy the chunkSize will be 0, so you have to specify the size of the first loaded chunk(the best value is `igxForContainerSize` divided on `igxForItemSize`).
```typescript
public getData(data?: IForOfState, cb?: (any) => void): any {
    var dataState = data;
    return this.http
        .get(this.buildUrl(dataState))
        .map((response) => response.json())
        .map((response) => {
            return response;
        })
        .subscribe((data) => {
            this._remoteData.next(data.value);
            if (cb) {
                cb(data);
            }
        });
}

private buildUrl(dataState: any): string {
    let qS: string = "?", requiredChunkSize: number;
    if (dataState) {
        const skip = dataState.startIndex;
            requiredChunkSize =  dataState.chunkSize === 0 ?
                // Set initial chunk size, the best value is igxForContainerSize divided on igxForItemSize
                10 : dataState.chunkSize;
        const top = requiredChunkSize;
        qS += `$skip=${skip}&$top=${top}&$count=true`;
    }
    return `${this.url}${qS}`;
}
```
And every time the `onChunkPreload` event is thrown the new chunk of data should be requested:
```typescript
chunkLoading(evt) {
    if(this.prevRequest){
        this.prevRequest.unsubscribe();
     }
     this.prevRequest = this.remoteService.getData(evt, ()=> {
        this.virtDirRemote.cdr.detectChanges();
    });
}
```
## API

### Inputs

Below is the list of all inputs that the developers may set to configure the `igxFor` look/behavior:
| Name | Type | Description |
| :--- |:--- | :--- |
| id | string | Unique identifier of the directive |
| `igxForOf` | any[] | The data to be virtualized |
| `igxForScrollOrientation` | string | Virtualization direction - "horizontal" or "vertical" |
| `igxForScrollContainer` | any | The container where the vertical and horizontal scrollbars will be created, the is useful when nesting the directive and for cases where the scrolling container is not going to be the direct parent |
| `igxForContainerSize` | any | Specifies the container size |
| `igxForItemSize` | any | Specifies the item size, when the virtualization is vertical it is used as height and as width when the virtualization is horizontal. It is mostly used for the vertical direction, because for the horizontal width it is possible to have items with different widhts |

### Accessors

List of public accessors that the developers may use to get information from the `igxFor`:
| Name | Type | Description |
| :--- |:--- | :--- |
| id | string | Unique identifier of the directive |
| `state` | IgxForState | The current state of the directive it contains `startIndex` and `chunkSize` |
| `totalItemCount` | number | The total count of the virtual data items, when using remote service |


### Outputs

A list of the events emitted by the **igx-for**:

| Name              | Description                                                          |
| :---------------- | :------------------------------------------------------------------- |
| _Event emitters_  | _Notify for a change_                                                |
| `OnChunkLoad`      | Used when scrolled to emit the loaded data item                      |
| `OnChunkPreload`   | Used when scrolled to emit the data item which is about to be loaded |


### Methods

Here is a list of all public methods exposed by the **igx-for**:

| Signature       | Description                     |
| :-------------- | :------------------------------ |
| `scrollNext()`  | Scrolls by one item into the  appropriate  next direction |
| `scrollPrev()`  | Scrolls by one item into the  appropriate  previous direction|
| `scrollTo(index)`  | Scrolls to the specified index |
