---
title: "Charting"
permalink: /features/charting
excerpt: "Drawing Charts from Table Result View"
toc: true
---

## Overview

One of another functionality available from [Table Result](/features/tables) is charting that can be invoked from main
toolbar or from pop-up menu:

![chartingButton](/assets/images/features/charting/chartingButton.png)

Charting is shown in separate windows and has own configuration and toolbars:

![img.png](/assets/images/features/charting/chartingDialog.png)

## Charts

### Line Chart

There are 3 main parts of any Line Charting:

![chartingLineSettings](/assets/images/features/charting/chartingLineSettings.png)

- **Domain axis** - any temporal or numerical column can be used as Domain or X axis
- **Series definition** - Each series has separate range on Y axis. usually you need only one but if you have price and
  size series with differ Y range you can use differ series to show differ ranges on the same chart
- **Range axes** - is exactly range axes, but you must select which Series it's belong to show it on the chart.

For example, for the following price/size data you can draw the following chart if only one series is used:

![chartingLineWrong](/assets/images/features/charting/chartingLineWrong.png)

As you can see, as price and size have differed ranges, the chart is useless. To fix the issue you can move size axis to
another series with own configuration:

![chartingLineCorrect](/assets/images/features/charting/chartingLineCorrect.png)

and here you can see _Price_ series on the left side and _Size_ series (you can rename series by double-click on the
cell) shown on the same chart but own range is used.

### Candlestick Chart

Primary proposal of [Candlestick Chart](https://en.wikipedia.org/wiki/Candlestick_chart) is to describe movements of
prices.

It is similar to a bar chart in that each candlestick represents all four important pieces of information for that day:
open and close in the thick body; high and low in the “candle wick”.

For example, you can create candlestick data source for trades base as:

~~~
select o:first price, h:max price, l:min price, c:last price, sum size by 3600000 xbar `time$time from trade
~~~

We can build candlestick like:
![chartingCandleStick](/assets/images/features/charting/chartingCandleStick.png)

Of course, the same data can be shown as a line chart, but it's much less informative:
![chartingCandleWrong](/assets/images/features/charting/chartingCandleWrong.png)

## Zoom and Move

You can use left mouse button drag to move the chart inside the frame.

You can use right mouse button drag to zoom an area of a chart.

## Charting Tools

### Crosshair

When enabled (enabled by default), shows crosshair with X and Y coordinates:

![chartingCrosshair](/assets/images/features/charting/chartingCrosshair.png)

### Measures

When enabled, allows measure distance from one point to another point on the chart.

Click one point on the chart and then click another point (don't drag as dragging move the chart itself) on the chart:
![chartingMeasures](/assets/images/features/charting/chartingMeasures.png)

Moving mouse down creates negative/red measure. Moving mouse up creates positive/green measure.

Use right-click to remove some or all measures from the chart.
{: .notice}

### Points Collector

When enabled, writes each mouse click on the chart into the table that can be exported to Excel, copied and sent to an
KDB instance:

![chartingPointsCollector](/assets/images/features/charting/chartingPointsCollector.png)

The _Key_ column contains pressed button market and modifier key, if pressed:

- **L** - left button
- **R** - right button
- **M** - middle button
- **S?** - click with shift pressed
- **C?** - click with ctrl pressed
- **CS?** - cick with shift and ctrl pressed

Using the market you can collect many point into one table at the same table. For example, by pressing left button for
high prices and right for low prices.

### Snapping

By default, any other charting tools are free-formed and can show any point on the chart, but sometimes real data is
required, and it's exactly where snapping can help:

![chartingSnapping](/assets/images/features/charting/chartingSnapping.png)

You can snap mouse movement to line only, and you can select any point on X axis but Y will be always auto-connected to
the chart line:

![chartingSnappingLine](/assets/images/features/charting/chartingSnappingLine.png)

You can snap mouse movement to line only, and you can select any point on X axis but Y will be always auto-connected to
the chart line:

![chartingSnappingLine](/assets/images/features/charting/chartingSnappingLine.png)

or you can use more strong snapping and bind X axis to chart points as well:

![chartingSnappingVertex](/assets/images/features/charting/chartingSnappingVertex.png)

## Export Image

You can copy and save the chart with appropriate tools in SVG or PNG formats if required. Nothing special here