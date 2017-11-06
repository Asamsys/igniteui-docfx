---
title: Tab Bar Component
_description: Display tabs for any occasion and implement a completely tabbed user interface. These UI controls manage every aspect of your tabs’ appearance and behavior.
_keywords: Ignite UI for Angular, UI controls, Angular widgets, web widgets, UI widgets, Angular, Native Angular Components Suite, Native Angular Controls, Native Angular Components Library, Angular Tab Bar component, Angular Tab Bar controls
---

## Tab Bar

### Usage
```html
<igx-tab-bar>
    <igx-tab-panel label="Tab 1">
        <h1>Tab 1 Content</h1>
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
    </igx-tab-panel>
    <igx-tab-panel label="Tab 2">
        <h1>Tab 2 Content</h1>
        <p>Lorem ipsum dolor sit amet...</p>
    </igx-tab-panel>
    <igx-tab-panel label="Tab 3">
        <h1>Tab 3 Content</h1>
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus vitae malesuada odio.</p>
    </igx-tab-panel>
</igx-tab-bar>
```

_Igx-Tab-Bar represents a single content area with multiple panels, each associated with a tab._
Igx-Tab-Bar provides two observable collections (QueryLists): one with panels and one with related tabs.
The children components of the Igx-Tab-Bar are:

- *Igx-Tab-Panel* - represents the wrapper of the content that needs to be displayed
- *Igx-Tab* - button that triggers displaying of the associated panel

Each tab (Igx-Tab) is related to particular panel (Igx-Tab-Panel). When tab is clicked, the associated panel is selected and visualized into a single container.
There should always be a selected tab. Only one tab can be selected at a time.

#### Tab Bar Properties
- `tabs` - Observable collection of all IgxTab view children
- `panels` - Observable collection of all IgxTabPanel content children
- `selectedIndex` - Gets the index of selected tab/panel in the respective collection. Default value: -1
- `selectedTab` - Gets the selected IgxTab in the tabbar based on `selectedIndex`

#### Events
- `onTabSelected` - Fired when new tab is selected
- `onTabDeselected` - Fired when tab is deselected

### Panel
*Igx-Tab-Panel* - _Child component of Igx-Tab-Bar, that represents the container of the content need to be displayed._

#### Panel Properties
- `isSelected` - Determines whether the panel is selected
- `isDisabled` - Determines whether the panel is disabled
- `index` - Gets the index of a panel in the panel collection
- `relatedTab` - Get the tab, associated with the panel
- `label` - Defines the label on the associated tab
- `icon` - Defines the icon on the associated tab

#### Panel Methods
- `select` - Select the panel and the associated tab

### Tab
*Igx-Tab* - _Child component of Igx-Tab-Bar, that represents the button that triggers displaying of the associated panel._

#### Tab Properties
- `isDisabled` - Determines whether the tab is disabled
- `isSelected` - Determines whether the tab is selected
- `index` - Gets the index of a tab in the tab collection
- `relatedPanel` - Get the panel, associated with the tab

#### Tab Methods
- `select` - Select the tab and the associated panel

### Tabbar Example
<div class="sample-container" style="height:600px">
    <iframe src='https://embed.plnkr.co/DOarGXGXOhO6BsWNdvhr/?show=preview&sidebar=false' width="100%" height="100%" seamless frameBorder="0"></inframe>
</div>