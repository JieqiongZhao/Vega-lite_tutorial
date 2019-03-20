## 1. Online Interactive Visualization Tool

### Vega-Lite online editing website

https://vega.github.io/editor/#/edited

Editing the visualization online with instant feedback

#### Tutorial Website

https://vega.github.io/vega-lite/tutorials/getting_started.html

#### Example Gallery

https://vega.github.io/vega-lite/examples/

## 2. Data Set

### Auto MPG Data Set

Original webpage: https://archive.ics.uci.edu/ml/datasets/auto+mpg

CSV file: http://pixel.ecn.purdue.edu:8080/~zhao413/car_mpg.csv

Json file: https://vega.github.io/vega-lite/data/cars.json

#### Description of variables:

##### Sample data items

| Miles_per_Gallon  | Cylinders | Displacement | Horsepower | Weight_in_lbs | Acceleration | Year | origin | Name|
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| 18 | 8 | 307 | 130 | 3504 | 12 | 1970-01-01 | USA | chevrolet chevelle malibu |
| 26  | 4 | 113 | 95 | 2372 | 15 | 1970-01-01 | Europe | volkswagen 1131 deluxe sedan |
| 24 | 4 | 113 | 95 | 2372 | 15 | 1970-01-01 | Japan | toyota corona mark ii |

1.mpg : continuous 

2.cylinders: multi-valued discrete 

3.displacement: continuous 

4.horsepower: continuous 

5.weight: continuous 

6.acceleration: continuous 

7.model year: multi-valued discrete 

8.origin: multi-valued discrete

9.car name: string (unique for each instance)

## 3. Analyze Data Using Visualization

### Single data column (one feature)

#### Histogram

One example with mpg, please try with other data columns

![](http://pixel.ecn.purdue.edu:8080/~zhao413/auto_mpg_hist_mpg.png)

[View this example in the online editor](https://vega.github.io/editor/#/url/vega-lite/N4KABGBEAkDODGALApgWwIaQFxUQFzwAdYsB6UgN2QHN0A6agSz0QFcAjOxge1IRQyUa6ALQAbZskoBmOgCtY3AHaQANOCgATdHkw5QECJFYAnMdi070peOhOx5ilRoC+6oxhMBrC5HZ21DUhkJXhuTUYlagsDQ0gADxiNQyh2SIs8E1ZkdxSoADNGZDFNXwBZRjFkWAB9QmQTGoBxdDExZUC8qDwAT3rfAEdWdCU8Zh1GKkhksDcZyB6krsh0amoTYTxkXzDWUc68yF7+nEghkbHdMamZl1cQFyA)

### Two data columns (a pair of features)
#### Scatterplot
Explore the correlation between two features.

![](http://pixel.ecn.purdue.edu:8080/~zhao413/auto_mpg_scatterplot_mpg_horsepower.png)

[View this example in the online editor](https://vega.github.io/editor/#/url/vega-lite/N4KABGBEAkDODGALApgWwIaQFxUQFzwAdYsB6UgN2QHN0A6agSz0QFcAjOxge1IRQyUa6ALQAbZskoBmOgCtY3AHaQANOCgATdHkw5QECJFYAnMdi070peOhOx5ilRoC+6oxhMBrC5ELdGJTw1DUhkJXhuTUDqCwNDSAAPOI1DKAAzRmQxTV8AWUYxZFgAfUJkExKAcXQxMWUQtKM8AE9y3wBHVnQg5h1GKkhUsDdhyBaUpoysnN8ACW57ZH8AdwrGpshW9pxILp68PsPB4ZdXEBcgA)

Color the data points with their origins.

![](http://pixel.ecn.purdue.edu:8080/~zhao413/auto_mpg_color_origin.png)

[View this example in the online editor](https://vega.github.io/editor/#/url/vega-lite/N4KABGBEAkDODGALApgWwIaQFxUQFzwAdYsB6UgN2QHN0A6agSz0QFcAjOxge1IRQyUa6ALQAbZskoBmOgCtY3AHaQANOCgATdHkw5QECJFYAnMdi070peOhOx5ilRoC+6oxhMBrC5ELdGJTw1DUhkJXhuTUDqCwNDSAAPOI1DKAAzRmQxTV8AWUYxZFgAfUJkExKAcXQxMWUQtKM8AE9y3wBHVnQg5h1GKkhUsDdhyBaUpoysnN8ACW57ZH8AdwrGpshW9pxILp68PsPB4dG0yEj6k0nNzOzc3YB5E0YmZzSXVxAXIA)

#### Some easy visual encoding variables to test with:

Mark: "line", "point", "bar", ...

Type: "temporal", "quantitative", "ordinal", ...

"transform": [{"filter": "datum.Origin==='Japan' || datum.Origin==='Europe'"}],

"shape": {"field": "Origin", "type": "nomimal"},

"color": {"field": "Origin"},

To avoid overlap, filter data samples by their origins.

![](http://pixel.ecn.purdue.edu:8080/~zhao413/auto_mpg_filter.png)

[View this example in the online editor](https://vega.github.io/editor/#/url/vega-lite/N4KABGBEAkDODGALApgWwIaQFxUQFzwAdYsB6UgN2QHN0A6agSz0QFcAjOxge1IRQyUa6ALQAbZskoBmOgCtY3AHaQANOCgATdHkw5QECJFYAnMdi070peOhOx5ilRoC+6oxhMBrC5ELdGJTw1DUg8E3QlWAAzbhNUCwBtYEhoxjE8ZBNfbTxWVDoAeRNGJiUAXkqAcgApdEJIqrAAH2awXPyikrLK8qqAUVNuQmQqyBcAXXcoZCV4bk1A6gsDQ0gADxWNQyg05DFNXwBZdORYAH0Rk3OAcXQxMWUQnaM8AE8R3wBHVki8Zh0jCokG2YDcoMgby2L12jH2hxwkAAEnFYMh-AB3LLPF5hD7Ib6-IIA-7A0HgnaQeaPbL6UFGPYHXzFUqBEE7FyuEAuIA)

More sophisticated interactive explore of scatterplot matrix:

https://vega.github.io/vega-lite/examples/interactive_splom.html


