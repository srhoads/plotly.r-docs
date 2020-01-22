---
description: How to draw a line on Map in R with plotly.
display_as: maps
language: r
layout: base
name: Lines on Mapbox
order: 10
output:
  html_document:
    keep_md: true
page_type: u-guide
permalink: r/lines-on-mapbox/
thumbnail: thumbnail/line_mapbox.jpg
---



### New to Plotly?

Plotly's R library is free and open source!<br>
[Get started](https://plot.ly/r/getting-started/) by downloading the client and [reading the primer](https://plot.ly/r/getting-started/).<br>
You can set up Plotly to work in [online](https://plot.ly/r/getting-started/#hosting-graphs-in-your-online-plotly-account) or [offline](https://plot.ly/r/offline/) mode.<br>
We also have a quick-reference [cheatsheet](https://images.plot.ly/plotly-documentation/images/r_cheat_sheet.pdf) (new!) to help you get started!

### Version Check

Version 4 of Plotly's R package is now [available](https://plot.ly/r/getting-started/#installation)!<br>
Check out [this post](http://moderndata.plot.ly/upgrading-to-plotly-4-0-and-above/) for more information on breaking changes and new features available in this version.

```r
library(plotly)
packageVersion('plotly')
```

```
## [1] '4.9.1'
```

### Mapbox Access Token

To plot on Mapbox maps with Plotly you *may* need a Mapbox account and a public [Mapbox Access Token](https://www.mapbox.com/studio). See our [Mapbox Map Layers](/r/mapbox-layers/) documentation for more information. If you're using a Chart Studio Enterprise server, please see additional instructions [here](https://help.plot.ly/mapbox-atlas).

### Lines on Mapbox maps using "Scattermapbox" traces

To draw a line on your map, you either can use [Scattermapbox](https://plot.ly/r/reference/#scattermapbox) or [scattergeo](https://plot.ly/r/reference/#scattergeo) trace type in plotly. This example uses scattermapbox and defines the drawing [mode](https://plot.ly/python/reference/#scattermapbox-mode) to the combination of markers and line.


```r
library(plotly)

p <- plot_ly(
  type = 'scattermapbox',
  mode = "markers+lines",
  lon = c(10, 20, 30),
  lat = c(10, 20,30),
  marker = list(size = 10)) %>%
  add_trace(
    type = 'scattermapbox',
    mode = "markers+lines",
    lon = c(-50, -60,40),
    lat = c(30, 10, -20),
    marker = list(size = 10)) %>%
  layout(
    mapbox = list(
      style = "stamen-terrain",
      center = list(lon = 10, lat= 10),
      zoom = 1),
    margin =list(l=0,t=0,b=0,r=0))

p
```

<div id="htmlwidget-2f938a922a100d79cbd8" style="width:672px;height:480px;" class="plotly html-widget"></div>
<script type="application/json" data-for="htmlwidget-2f938a922a100d79cbd8">{"x":{"visdat":{"34fc21397f70":["function () ","plotlyVisDat"]},"cur_data":"34fc21397f70","attrs":{"34fc21397f70":{"mode":"markers+lines","lon":[10,20,30],"lat":[10,20,30],"marker":{"size":10},"alpha_stroke":1,"sizes":[10,100],"spans":[1,20],"type":"scattermapbox"},"34fc21397f70.1":{"mode":"markers+lines","lon":[-50,-60,40],"lat":[30,10,-20],"marker":{"size":10},"alpha_stroke":1,"sizes":[10,100],"spans":[1,20],"type":"scattermapbox","inherit":true}},"layout":{"margin":{"b":0,"l":0,"t":0,"r":0},"mapbox":{"style":"stamen-terrain","center":{"lon":10,"lat":10},"zoom":1},"hovermode":"closest","showlegend":true},"source":"A","config":{"showSendToCloud":false},"data":[{"mode":"markers+lines","lon":[10,20,30],"lat":[10,20,30],"marker":{"color":"rgba(31,119,180,1)","size":10,"line":{"color":"rgba(31,119,180,1)"}},"type":"scattermapbox","line":{"color":"rgba(31,119,180,1)"},"frame":null},{"mode":"markers+lines","lon":[-50,-60,40],"lat":[30,10,-20],"marker":{"color":"rgba(255,127,14,1)","size":10,"line":{"color":"rgba(255,127,14,1)"}},"type":"scattermapbox","line":{"color":"rgba(255,127,14,1)"},"frame":null}],"highlight":{"on":"plotly_click","persistent":false,"dynamic":false,"selectize":false,"opacityDim":0.2,"selected":{"opacity":1},"debounce":0},"shinyEvents":["plotly_hover","plotly_click","plotly_selected","plotly_relayout","plotly_brushed","plotly_brushing","plotly_clickannotation","plotly_doubleclick","plotly_deselect","plotly_afterplot","plotly_sunburstclick"],"base_url":"https://plot.ly"},"evals":[],"jsHooks":[]}</script>
#Reference

See [https://plot.ly/r/reference/#scattermapbox](https://plot.ly/r/reference/#scattermapbox) for more information and options!