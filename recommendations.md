---
layout: page
title: Recommendations
permalink: /brian-landru/recommendations/
---

<head>
    <!-- ...other head elements... -->
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400&display=swap" rel="stylesheet">
</head>

<style>
  @keyframes slideInFromLeft {
    0% {
      transform: translateX(-100%);
    }
    100% {
      transform: translateX(0);
    }
  }

  .slide-in-left {
    opacity: 0; /* Start elements as invisible */
    transform: translateX(-100%);
  }

  .slide-in-left.start-slide-in {
    opacity: 1;
    transform: translateX(0);
    animation: slideInFromLeft 0.5s ease-out forwards;
  }
</style>

<!-- # {{ page.title }} -->

<!-- Slide-in table -->
<div class="slide-in-left">
  <table>
    <thead>
      <tr>
        <th>Recommended Tenant Type</th>
        <th>Score</th>
        <!-- more columns as necessary -->
      </tr>
    </thead>
    <tbody>
      {% for item in site.data.data %}
      <tr>
        <td>{{ item.a }}</td>
        <td>{{ item.b | times: 100 | round: 0 | append: "%" }}</td>
        <!-- more data items as necessary -->
      </tr>
      {% endfor %}
    </tbody>
  </table>
</div>

<!-- Slide-in SVG image -->
<div class="slide-in-left">
  <img src="{{ 'assets/images/cotenant_impact.svg' | relative_url }}" alt="Description of SVG">
</div>

more text 

<!-- Slide-in SVG image -->
<div class="slide-in-left">
  <img src="{{ 'assets/images/metric_changes.svg' | relative_url }}" alt="Description of SVG">
</div>

text

more text 





<!-- <html lang="en">
<head>
    <meta charset="UTF-8">
    <title>D3 Graph</title>
    <script src="https://d3js.org/d3.v6.min.js"></script>
    <style>
        svg {
            background-color: #222;
            color: white;
        }
        .line {
            fill: none;
            stroke: #FFD700;
            stroke-width: 2;
        }
        .area {
            fill: gold;
            opacity: 0.5;
        }
        .property-line {
            fill: none;
            stroke: white;
            stroke-width: 2;
            stroke-dasharray: 5,5;
        }
    </style>
</head>
<body>
    <div id="graph"></div>

    <script>
        // Placeholder data for the KDE plot
        const data = Array.from({ length: 100 }, (_, i) => ({
            x: i / 100,
            y: Math.random() // Random values for demonstration
        }));

        // Width and height for your SVG
        const width = 960;
        const height = 500;

        // Create SVG element
        const svg = d3.select("#graph")
            .append("svg")
            .attr("width", width)
            .attr("height", height);

        // Create scales
        const xScale = d3.scaleLinear()
            .domain(d3.extent(data, d => d.x))
            .range([0, width]);

        const yScale = d3.scaleLinear()
            .domain([0, d3.max(data, d => d.y)])
            .range([height, 0]);

        // Define the area
        const area = d3.area()
            .x(d => xScale(d.x))
            .y0(height)
            .y1(d => yScale(d.y));

        // Add the area under the KDE
        svg.append("path")
            .datum(data)
            .attr("class", "area")
            .attr("d", area);

        // Define the line
        const line = d3.line()
            .x(d => xScale(d.x))
            .y(d => yScale(d.y));

        // Add the KDE line
        svg.append("path")
            .datum(data)
            .attr("class", "line")
            .attr("d", line);

        // Add a vertical line for the specific property's metric value (placeholder value)
        const propertyMetricValue = 0.5; // This is a placeholder value
        svg.append("line")
            .attr("class", "property-line")
            .attr("x1", xScale(propertyMetricValue))
            .attr("y1", 0)
            .attr("x2", xScale(propertyMetricValue))
            .attr("y2", height);
    </script>
</body>
</html> -->

<script>
  document.addEventListener('DOMContentLoaded', function () {
    var elements = document.querySelectorAll('.slide-in-left');

    function isElementInView(element) {
      var rect = element.getBoundingClientRect();
      return (
        rect.top >= 0 &&
        rect.left >= 0 &&
        rect.bottom <= (window.innerHeight || document.documentElement.clientHeight) &&
        rect.right <= (window.innerWidth || document.documentElement.clientWidth)
      );
    }

    function checkPosition() {
      for (var i = 0; i < elements.length; i++) {
        if (isElementInView(elements[i])) {
          elements[i].classList.add('start-slide-in');
        }
      }
    }

    window.addEventListener('scroll', checkPosition);
    checkPosition();
  });
</script>