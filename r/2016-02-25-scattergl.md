---
name: WebGL vs SVG in R
permalink: r/webgl-vs-svg/
redirect_from: r/webgl-vs-svg-line-chart/
description: How to create plots using WebGL
layout: base
thumbnail: thumbnail/webgl.jpg
language: r
display_as: basic
order: 7
output:
  html_document:
    highlight: null
    keep_md: true
    theme: null
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

# WebGL vs SVG in R

Recent versions of the R package include the `toWebGL()` function, which converts any eligible SVG graph into a WebGL plot. With WebGL, we can render way more elements in the browser.

## WebGL with 50,000 points


```r
library(plotly)
p <- ggplot(data = diamonds, aes(x = carat, y = price, color = cut)) +
  geom_point(alpha = 0.01)
p <- ggplotly(p) %>% toWebGL()

p
```

<div id="htmlwidget-9215a54e3056dfe5b709" style="width:672px;height:480px;" class="plotly html-widget"></div>

## More examples

* [Compare SVG performance to WebGL](https://plot.ly/r/webgl-vs-svg/)
* [WebGL with 1 million points](https://plot.ly/r/webgl-vs-svg-million-points/)
* [WebGL for time series](https://plot.ly/r/webgl-vs-svg-time-series/)