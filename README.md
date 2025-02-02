# ChartSpan

ChartSpan is a Python library designed for rendering Vega-Lite JSON specifications directly within Google Colab. It simplifies the visualization of interactive charts and supports customization for chart dimensions, text color, and background color.

## Features

- **Inline Rendering**: Renders Vega-Lite JSON specifications directly within Google Colab.
- **Interactive Charts**: Maintains full Vega-Lite interactivity (e.g., zoom, pan, tooltips).
- **Custom Dimensions**: Easily adjust chart width and height for different use cases.
- **Text Color Customization**: Allows specifying custom colors for text elements.
- **Background Color Customization**: Supports setting a custom background color for charts.
- **Lightweight and Easy-to-Use**: Minimal setup and dependencies.

## Installation

To install ChartSpan, use pip:

```bash
pip install chartspan
```

## Usage

### Rendering Vega-Lite JSON Charts

Here is an example of how to use ChartSpan to render a Vega-Lite JSON chart:

```python
from chartspan import ChartSpan
import json

# Load Vega-Lite JSON specification
with open("example.json", "r") as f:
    spec = json.load(f)

# Render chart inline
chart = ChartSpan(width=800, height=600)
chart.render_inline(spec)
```

### Customization

You can specify custom dimensions for the chart:

```python
chart = ChartSpan(width=1000, height=800)
chart.render_inline(spec)
```

You can also customize the text color for labels, titles, legends, and axes:

```python
chart = ChartSpan(width=800, height=600, text_color="blue")
chart.render_inline(spec)
```

Alternatively, you can override the default text color for a specific chart:

```python
chart = ChartSpan(width=800, height=600, text_color="black")
chart.render_inline(spec, text_color="red")
```

You can also customize the background color of the chart:

```python
chart = ChartSpan(width=800, height=600, text_color="black")
chart.render_inline(spec, background_color="lightgray")
```

This modifies the chart's width, height, text color, and background color, ensuring it fits your specific needs and visual style.

## Example

Save the following Vega-Lite JSON to a file named `example.json`:

```json
{
  "$schema": "https://vega.github.io/schema/vega-lite/v5.json",
  "mark": "point",
  "data": {
    "values": [
      {"x": 1, "y": 2},
      {"x": 2, "y": 3}
    ]
  },
  "encoding": {
    "x": {"field": "x", "type": "quantitative"},
    "y": {"field": "y", "type": "quantitative"}
  }
}
```

Run the following Python code:

```python
from chartspan import ChartSpan
import json

with open("example.json", "r") as f:
    spec = json.load(f)

chart = ChartSpan(width=800, height=600, text_color="#dcdfe1")
chart.render_inline(spec, background_color="#353535")
```

This will display an interactive scatter plot in your Google Colab environment, with labels and titles rendered in green and a light blue background.

## Dependencies

- `IPython`

Install dependencies using:

```bash
pip install IPython
```

## License

ChartSpan is licensed under the MIT License.

## Contributing

Contributions are welcome! If you'd like to contribute, please fork the repository and submit a pull request.

## Acknowledgments

ChartSpan uses the Vega-Lite and Vega-Embed libraries for rendering charts. Special thanks to the developers of these powerful visualization tools.
