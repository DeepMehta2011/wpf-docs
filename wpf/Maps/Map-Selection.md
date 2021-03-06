---
layout: post
title: Map Selection | SfMap | wpf | Syncfusion
description: This section describes how to use Selection support WPF SfMaps control with SelectedShapeColor, SelectedMapShapes properties.
platform: wpf
control: SfMap
documentation: ug
---

# Map Selection in WPF Maps (SfMap)

Each shape in the map can be selected and unselected when interacted with shapes. There are two ways to select the map shapes:

1. Single Selection 
2. Multi Selection

The selected map shapes is differentiate by its fill. [`SelectedShapeColor`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Maps.ShapeSetting.html#Syncfusion_UI_Xaml_Maps_ShapeSetting_SelectedShapeColor) of `ShapeSetting` is the API that is used to get or set the selected shape color.

All selected shapes available in the [`SelectedMapShapes`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Maps.ShapeFileLayer.html#Syncfusion_UI_Xaml_Maps_ShapeFileLayer_SelectedMapShapes) of ShapeFileLayer.

## Single Selection

Single selection allows only one shape to be selected at a time. You can select the shape by clicking or tapping on the shape. Single selection is enabled by the [`EnableSelection`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Maps.ShapeFileLayer.html#Syncfusion_UI_Xaml_Maps_ShapeFileLayer_EnableSelection) property of ShapeFileLayer. When `EnableSelection` is set to true, then the map can be selected. When it is set to false, the shapes cannot be selected. When any other shape or the map area is selected, then the shape that is already selected is unselected.

## Multi Selection

Multiple shapes in the map can be selected when [`EnableMultiSelection`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Maps.ShapeFileLayer.html#Syncfusion_UI_Xaml_Maps_ShapeFileLayer_EnableMultiSelection) of ShapeFileLayer is set to true. When EnableMultiSelection is set to true, a cross-hair cursor appears on the map to guide the selection. When you drag on the map, a rectangle appears. The shapes bound that intersect with the rectangle is selected. When EnableMultiSelection is set to true, the panning does not work through interactions.

{% highlight xaml %}

        <syncfusion:SfMap >
            <syncfusion:SfMap.Layers>
                <syncfusion:ShapeFileLayer x:Name="shapeLayer" CrossCursorStroke="#686868" 
                                           CrossCursorStrokeThickness="0.5" EnableSelection ="True"
                                           EnableMultiSelection="True"
                                           Uri="DataMarkers.ShapeFiles.world1.shp">
                    <syncfusion:ShapeFileLayer.ShapeSettings>
                        <syncfusion:ShapeSetting ShapeFill="#E5E5E5" SelectedShapeColor="#1196CD" 
                                                 ShapeStroke="#C1C1C1" ShapeStrokeThickness="1" />
                    </syncfusion:ShapeFileLayer.ShapeSettings>
                </syncfusion:ShapeFileLayer>
            </syncfusion:SfMap.Layers>
        </syncfusion:SfMap>

{% endhighlight %}


![Maps control selection](Map-Selection_images/Map-Selection_img1.png)



![Maps control selection](Map-Selection_images/Map-Selection_img2.png)


