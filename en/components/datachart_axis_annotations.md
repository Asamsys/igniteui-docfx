---
title: Data Chart | Visualization Tools | Ignite UI for Angular | Infragistics | Axis Annotations
_description: Create a data chart that displays multiple instances of visual elements in the same plot area in order to create composite chart views.
_keywords: data chart, Ignite UI for Angular, Infragistics
mentionedTypes: ['XamDataChart']
---

## Axis Annotations

In the Ignite UI for Angular data chart component, you are able to add annotations to your axes to show particular values at different points on that axis. This can help you to visualize things such as final series values, overlay values, and values corresponding to crosshairs in the chart.

### Demo

<div class="sample-container loading" style="height: 450px">
    <iframe id="data-chart-axis-locations-iframe" src='{environment:demosBaseUrl}/charts/data-chart-axis-annotations' width="100%" height="100%" seamless frameBorder="0" onload="onXPlatSampleIframeContentLoaded(this);"></iframe>
</div>
<div>
    <button data-localize="stackblitz" disabled class="stackblitz-btn" data-iframe-id="data-chart-axis-locations-iframe" data-demos-base-url="{environment:demosBaseUrl}">View on StackBlitz
    </button>
</div>

<div class="divider--half"></div>

In the Ignite UI for Angular data chart, the following are the series and layers that support axis annotations:

-   [`IgxCrosshairLayerComponent`](/components/datachart_axis_annotations.html)
-   [`IgxFinalValueLayerComponent`](/components/datachart_axis_annotations.html)
-   [`IgxValueOverlayComponent`](/components/datachart_axis_annotations.html)

You can enable the axis annotations by setting the [`isAxisAnnotationEnabled`](/components/datachart_axis_annotations.html) property of the corresponding layer or overlay to `true`. In doing so, this will place a box on the corresponding owning axis or axes with the value that that particular overlay or layer represents at the point that it is currently at. For example, with the [`IgxCrosshairLayerComponent`](/components/datachart_axis_annotations.html), these annotations can appear on both the X and Y axes and will move around and change as you scroll around the plot area.

The [`isAxisAnnotationEnabled`](/components/datachart_axis_annotations.html) property does not exist on the [`IgxFinalValueLayerComponent`](/components/datachart_axis_annotations.html), as this layer is an axis annotation in itself and has no other visualization other than the annotation on the axis.

You can customize the axis annotations in background, value precision, outline, padding, stroke (outline) thickness, and text color. These can be set using the [`axisAnnotationBackground`](/components/datachart_axis_annotations.html), [`axisAnnotationInterpolatedValuePrecision`](/components/datachart_axis_annotations.html), [`axisAnnotationOutline`](/components/datachart_axis_annotations.html), `AxisAnnotationPadding`, [`axisAnnotationStrokeThickness`](/components/datachart_axis_annotations.html), and [`axisAnnotationTextColor`](/components/datachart_axis_annotations.html) properties, respectively. In addition to these properties, there is also an `AxisAnnotationFormatLabel` event that you can use to fully customize what exactly is shown in axis annotations.

Note, the [`IgxCrosshairLayerComponent`](/components/datachart_axis_annotations.html) has the ability to show annotations on both the X and Y axis. These can be customized individually, and as such, each of the above properties exist, but with either an `XAxis` or a `YAxis` placed in front of the name. For example, [`xAxisAnnotationBackground`](/components/datachart_axis_annotations.html) or [`yAxisAnnotationTextColor`](/components/datachart_axis_annotations.html).

### Code Example

This code demonstrates how to create a Ignite UI for Angular data chart with each of the layers and the overlay with axis annotations enabled for each. In this case, the [`IgxFinalValueLayerComponent`](/components/datachart_axis_annotations.html) is also customized to have a yellow text color.

```html
<igx-data-chart [dataSource]="data" width="100%" height="500px">
    <igx-category-x-axis #xAxis label="label"></igx-category-x-axis>
    <igx-numeric-y-axis #yAxis></igx-numeric-y-axis>

    <igx-column-series [xAxis]="xAxis" [yAxis]="yAxis" valueMemberPath="value"></igx-column-series>

    <igx-value-overlay [axis]="yAxis" isAxisAnnotationsEnabled=true thickness=3 value=85></igx-value-overlay>

    <igx-crosshair-layer isAxisAnnotationsEnabled=true></igx-crosshair-layer>

    <igx-final-value-layer axisAnnotationTextColor="Yellow"></igx-final-value-layer>                
</igx-data-chart>
```

### Additional Resources

-   [Data Chart Series Annotations](datachart_series_annotations.md)
-   [Value Overlay](datachart_series_value_overlay.md)