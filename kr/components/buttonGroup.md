---
title: Button Group Component
_description: Provides button group functionality to developers and also allows horizontal/vertical alignment, single/multiple selection with toggling.
_keywords: Ignite UI for Angular, UI controls, Angular widgets, web widgets, UI widgets, Angular, Native Angular Components Suite, Native Angular Controls, Native Angular Components Library, Angular Button Group components, Angular Button Group controls, Angular Buttons components, Angular Buttons controls
_language: kr
---

## Button Group
The [**igx-buttongroup**]({environment:angularApiUrl}/classes/igxbuttongroupcomponent.html) component in Ignite UI for Angular provides a button group functionality with horizontal/vertical alignment and single/multiple selection along with toggling. The igx-buttongroup component makes use of the [igxButton directive.](button.md)

### Button Group Demo
<div class="sample-container loading" style="height: 400px">
    <iframe id="buttonGroup-sample-1-iframe" seamless="" width="100%" height="100%" frameborder="0" src="{environment:demosBaseUrl}/data-entries/button-group-sample-1" onload="onSampleIframeContentLoaded(this);">
</iframe></div>
<div>
<button data-localize="stackblitz" disabled class="stackblitz-btn" data-iframe-id="buttonGroup-sample-1-iframe" data-demos-base-url="{environment:demosBaseUrl}">StackBlitz 에서보기</button>
</div>
<div class="divider--half"></div>

### Dependencies
The Button Group is exported as an `NgModule`, thus you will need to import the `IgxButtonGroupModule` inside your `AppModule`:

```typescript
// app.module.ts

import { IgxButtonGroupModule } from 'igniteui-angular';

@NgModule({
    imports: [
        ...
        IgxButtonGroupModule,
        ...
    ]
})
export class AppModule {}
```
### Usage
Use [`igx-buttongroup`]({environment:angularApiUrl}/classes/igxbuttongroupcomponent.html) to organize buttons into an Angular styled button group.

#### Alignment
Use the [`alignment`]({environment:angularApiUrl}/classes/igxbuttongroupcomponent.html#alignment) input to set the orientation of the buttons in the button group.

```typescript
//sample.component.ts

import { ButtonGroupAlignment } from "igniteui-angular";
...
public alignment = ButtonGroupAlignment.vertical;
...
```

```html
<!-- sample.component.html -->

<igx-buttongroup [alignment]="alignment">
    <button igxButton>Sofia</button>
    <button igxButton>London</button>
    <button igxButton [selected]="true">New York</button>
    <button igxButton>Tokyo</button>
</igx-buttongroup>
```

```scss
// sample.component.scss

igx-buttongroup{
    display: inline-block;
    width: 200px;
}
```
<div class="sample-container loading" style="height: 164px">
    <iframe id="buttonGroup-sample-2-iframe" seamless="" width="100%" height="100%" frameborder="0" data-src="{environment:demosBaseUrl}/data-entries/button-group-sample-2" class="lazyload">
</iframe></div>
<div>
<button data-localize="stackblitz" disabled class="stackblitz-btn" data-iframe-id="buttonGroup-sample-2-iframe" data-demos-base-url="{environment:demosBaseUrl}">view on stackblitz</button>
</div>
<div class="divider--half"></div>

#### Multiple selection
Use the the [`multiSelection`]({environment:angularApiUrl}/classes/igxbuttongroupcomponent.html#multiselection) input to enable the multiple selection in the button group.

```html
<!-- sample.component.html -->

<igx-buttongroup [multiSelection]="true">
    <button igxButton>
        <igx-icon>format_bold</igx-icon>
    </button>
    <button igxButton>
        <igx-icon>format_italic</igx-icon>
    </button>
    <button igxButton>
        <igx-icon>format_underlined</igx-icon>
    </button>
</igx-buttongroup>
```
<div class="sample-container loading" style="height: 60px">
    <iframe id="buttonGroup-sample-4-iframe" seamless="" width="100%" height="100%" frameborder="0" data-src="{environment:demosBaseUrl}/data-entries/button-group-sample-4" class="lazyload">
</iframe></div>
<div>
<button data-localize="stackblitz" disabled class="stackblitz-btn" data-iframe-id="buttonGroup-sample-4-iframe" data-demos-base-url="{environment:demosBaseUrl}">view on stackblitz</button>
</div>

#### Display Density
Use the [`displayDensity`]({environment:angularApiUrl}/classes/igxbuttongroupcomponent.html#displaydensity) input to set the display density for the button group. This will set the style for the buttons in the group to cosy, compact or comfortable (default value) accordingly.

> [!NOTE] The display density of a button within a button group is not changed if it is explicitly specified.

```typescript
// sample.component.ts

...
public displayDensity = "comfortable";
public displayDensities;

public ngOnInit() {
    this.displayDensities = [
        { label: "cosy", selected: this.displayDensity === "cosy", togglable: true },
        { label: "compact", selected: this.displayDensity === "compact", togglable: true },
        { label: "comfortable", selected: this.displayDensity === "comfortable", togglable: true }
    ];
}

public selectDensity(event) {
    this.displayDensity = this.displayDensities[event.index].label;
}
...
```

```html
<!-- sample.component.html -->

<article class="sample-column">
    <igx-buttongroup [multiSelection]="false" [values]="displayDensities" (onSelect)="selectDensity($event)"
        [displayDensity]="displayDensity">
    </igx-buttongroup>
</article>
```
<div class="sample-container loading" style="height: 60px">
    <iframe id="buttonGroup-sample-5-iframe" seamless="" width="100%" height="100%" frameborder="0" data-src="{environment:demosBaseUrl}/data-entries/button-group-sample-5" class="lazyload">
</iframe></div>
<div>
<button data-localize="stackblitz" disabled class="stackblitz-btn" data-iframe-id="buttonGroup-sample-5-iframe" data-demos-base-url="{environment:demosBaseUrl}">view on stackblitz</button>
</div>

#### Custom toggle buttons
Use the [`values`]({environment:angularApiUrl}/classes/igxbuttongroupcomponent.html#values) input to set an array of customized buttons in the button group.

```typescript
// sample.component.ts

interface IButton {
    ripple?: string;
    label?: string;
    disabled?: boolean;
    togglable?: boolean;
    selected?: boolean;
    color?: string;
    icon?: string;
}

class ToggleButton {
    private ripple: string;
    private label: string;
    private disabled: boolean;
    private togglable: boolean;
    private selected: boolean;
    private color: string;
    private icon: string;

    constructor(obj?: IButton) {
        this.ripple = obj.ripple || "gray";
        this.label = obj.label;
        this.selected = obj.selected || false;
        this.togglable = obj.togglable || true;
        this.disabled = obj.disabled || false;
        this.color = obj.color;
        this.icon = obj.icon;
    }
}
...
public bordersButtons: ToggleButton[];

public ngOnInit() {
    this.bordersButtons = [
        new ToggleButton({
            icon: "border_top",
            selected: true
        }),
        new ToggleButton({
            icon: "border_right",
            selected: false
        }),
        new ToggleButton({
            icon: "border_bottom",
            selected: false
        }),
        new ToggleButton({
            icon: "border_left",
            selected: false
        })
    ];
}
...
```

```html
<!-- sample.component.html -->

<igx-buttongroup [multiSelection]="true" [values]="borders"></igx-buttongroup>
```

<div class="sample-container loading" style="height: 60px">
    <iframe id="buttonGroup-sample-3-iframe" seamless="" width="100%" height="100%" frameborder="0" data-src="{environment:demosBaseUrl}/data-entries/button-group-sample-3" class="lazyload">
</iframe></div>
<div>
<button data-localize="stackblitz" disabled class="stackblitz-btn" data-iframe-id="buttonGroup-sample-3-iframe" data-demos-base-url="{environment:demosBaseUrl}">view on stackblitz</button>
</div>

### API References
<div class="divider--half"></div>

* [IgxButtonDirective]({environment:angularApiUrl}/classes/igxbuttondirective.html)
* [IgxButtonGroupComponent]({environment:angularApiUrl}/classes/igxbuttongroupcomponent.html)
* [IgxButtonGroup Styles]({environment:sassApiUrl}/index.html#function-igx-button-group-theme)

### Additional Resources
<div class="divider--half"></div>

Our community is active and always welcoming to new ideas.

* [Ignite UI for Angular **Forums**](https://www.infragistics.com/community/forums/f/ignite-ui-for-angular)
* [Ignite UI for Angular **GitHub**](https://github.com/IgniteUI/igniteui-angular)

