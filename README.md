!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
</head>
<body>
    
    <div id="draw-here"></div>
    
    <script>
        
    </script>
</body>
</html>


2:  Svg html

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Scalable Vector Graphics</title>
</head>
<body>
    <h1>Data Visualisation</h1>

    <h2>Scalable Vector Graphics</h2>


    <!--<svg>-->
    <!--    <rect x="0" y="0" width="100" height="50" fill="red"/>-->
    <!--    <circle cx="100" cy="25" r="20" fill="blue"/>-->
    <!--</svg>-->

    <svg>
        <polygon points="0,0 100,0 200,100 250,50 300,300 0,300"
    </svg>

    <h3>Rectangle</h3>
    <svg>
        <rect x="0" y="0" width="100" height="50"/>
    </svg>

    <h3>Circle</h3>
    <svg>
        <circle cx="50" cy="30" r="30"/>
    </svg>

    <h3>Ellipse</h3>
    <svg>
        <ellipse cx="100" cy="20" rx="50" ry="20"/>
    </svg>

    <h3>Polygon</h3>
    <svg>
        <polygon points="100,0 120,0 130,10 115,40 90,20"/>
    </svg>

    <h3>Composite Image</h3>
    <svg>
        <rect x="0" y="0" width="20" height="20"/>
        <circle cx="50" cy="30" r="30"/>
        <ellipse cx="200" cy="30" rx="50" ry="20"/>

        <polygon points="100,0 120,0 130,10 115,40 90,20"/>
    </svg>

    <h3>Bar Chart</h3>
    <svg>
        <rect x="0" y="0" width="19" height="150"/>
        <rect x="20" y="20" width="19" height="130"/>
        <rect x="40" y="50" width="19" height="100"/>
        <rect x="60" y="10" width="19" height="140"/>
        <rect x="80" y="100" width="19" height="50"/>
        <rect x="100" y="30" width="19" height="120"/>
        <rect x="120" y="40" width="19" height="110"/>
    </svg>

    <h3>Colour</h3>
    <svg>
        <rect x="0" y="0" width="19" height="150" fill="red"/>
        <rect x="20" y="20" width="19" height="130" fill="orange"/>
        <rect x="40" y="50" width="19" height="100" fill="yellow"/>
        <rect x="60" y="10" width="19" height="140" fill="green"/>
        <rect x="80" y="100" width="19" height="50" fill="blue"/>
        <rect x="100" y="30" width="19" height="120" fill="indigo"/>
        <rect x="120" y="40" width="19" height="110" fill="violet"/>
    </svg>
</body>
</html>


3: data driven documents
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Data Driven Documents</title>

    <script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/d3/3.5.17/d3.min.js"></script>
</head>
<body>
    <h1>Data Visualisation</h1>

    <h2>Data Driven Documents</h2>

    <div id="draw-here"></div>

    <script>
    var data = [
        {"name": "Donald Duck", "bio":"First appeared in the 1934 cartoon The Wise Little Heon."},
        {"name": "Mickey Mouse", "bio":"The first Mickey Mouse cartoon actually completed was Plane Crazy"},
        {"name": "Minnie Mouse", "bio":"First appeared in Steamboad Willie, in 1928."},
        {"name": "Goofy", "bio":"First appearance in 1932's Mickey's Revue."},
    ];
    //Create SVG element
    var doc = d3.select("#draw-here");
    var doc_item = doc.selectAll("div")
        .data(data)
        .enter()
        .append("div");
    doc_item.append("h4").text(function (d) {
        return d.name;
    });
    doc_item.append("p").text(function (d) {
        return d.bio;
    });
    </script>
</body>
</html>


3: d3 and svg
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>D3 and Scalable Vector Graphics</title>

    <script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/d3/3.5.17/d3.min.js"></script>
</head>
<body>
    <h1>Data Visualisation</h1>

    <h2>D3 and Scalable Vector Graphics</h2>

    <div id="draw-here"></div>

    <script>
    var w = 500;
    var h = 200;
    var data = [40, 50, 10, 30, 20];
    //Create SVG element
    var svg = d3.select("#draw-here")
        .append("svg")
        .attr("width", w)
        .attr("height", h);
    svg.selectAll("circle")
        .data(data)
        .enter()
        .append("circle")
        .attr("cx", function (d, i) {
            return 50 + (i * 100);
        })
        .attr("cy", h / 2)
        .attr("r", function (d) {
            return d;
        });
    </script>
</body>
</html>

4:d3 charting
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>D3 and Scalable Vector Graphics</title>

    <script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/d3/3.5.17/d3.min.js"></script>
</head>
<body>
    <h1>Data Visualisation</h1>

    <h2>D3 Charting</h2>

    <div id="draw-here"></div>

    <script>
    var w = 500;
    var h = 500;
    var barPadding = 1;
    var dataset = [
        450, 100, 100, 279, 500, 25, 350, 120, 80, 130,
        110, 102, 375, 200, 175, 168, 180, 230, 205,
    ];
    var svg = d3.select("#draw-here")
        .append("svg")
        .attr("width", w)
        .attr("height", h);
    svg.selectAll("rect")
        .data(dataset)
        .enter()
        .append("rect")
        .attr("x", function(d, i) {
            return i * (w / dataset.length);
        })
        .attr("y", function(d) {
            return h - d;
        })
        .attr("width", w / dataset.length - barPadding)
        .attr("height", function(d) {
            return d;
        });
    svg.selectAll("text")
        .data(dataset)
        .enter()
        .append("text")
        .text(function(d) {
            return d;
        })
        .attr("text-anchor", "middle")
        .attr("x", function(d, i) {
            return i * (w / dataset.length) + (w / dataset.length - barPadding) / 2;
        })
        .attr("y", function(d) {
            return h - d + 14;
        })
        .attr("font-family", "sans-serif")
        .attr("font-size", "11px")
        .attr("fill", "white");
    </script>
</body>
</html>

5:  d3 log scale

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>D3 and Scalable Vector Graphics</title>

    <script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/d3/3.5.17/d3.min.js"></script>

</head>
<body>
    <h1>Data Visualisation</h1>

    <h2>D3 Logarithmic Scale</h2>

    <div id="draw-here"></div>

    <script>
    var w = 500;
    var h = 500;
    var barPadding = 1;
    var dataset = [
        5, 10, 100, 279, 500, 25, 750, 1200, 800, 1300,
        110, 102, 15, 200, 175, 168, 180, 230, 205,
    ];
    var scale = d3.scale.log();
    scale.domain([5, 1300]);
    scale.range([0, 500]);
    var svg = d3.select("#draw-here")
        .append("svg")
        .attr("width", w)
        .attr("height", h);
    svg.selectAll("rect")
        .data(dataset)
        .enter()
        .append("rect")
        .attr("x", function(d, i) {
            return i * (w / dataset.length);
        })
        .attr("y", function(d) {
            return h - scale(d);
        })
        .attr("width", w / dataset.length - barPadding)
        .attr("height", function(d) {
            return scale(d);
        });
    svg.selectAll("text")
        .data(dataset)
        .enter()
        .append("text")
        .text(function(d) {
            return d;
        })
        .attr("text-anchor", "middle")
        .attr("x", function(d, i) {
            return i * (w / dataset.length) + (w / dataset.length - barPadding) / 2;
        })
        .attr("y", function(d) {
            return h - scale(d) + 14;
        })
        .attr("font-family", "sans-serif")
        .attr("font-size", "11px")
        .attr("fill", "white");
    </script>
</body>
</html>


6: change data
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>D3 and Scalable Vector Graphics</title>

    <script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/d3/3.5.17/d3.min.js"></script>
</head>
<body>
    <h1>Data Visualisation</h1>

    <h2>D3 Charting</h2>

    <button onclick="change_data()">Change Data</button>
    <button onclick="filtered_data()">Filtered Data</button>
    <input type=text id="filter_value" placeholder="Minimum required (100)"/>
    <hr>
    
    <div id="draw-here"></div>

    <script>
    
    // Size of Chart
    var w = 500;
    var h = 500;
    var barPadding = 1;
    var numberOfBars = 19;
    
    // Useful Variables
    colWidth = w / numberOfBars;
    barWidth = colWidth - barPadding;
    // Create an SVG element
    var svg = d3.select("#draw-here")
        .append("svg")
        .attr("width", w)
        .attr("height", h);
    // First Call to change_data will plot the initial chart
    change_data();
    // Generates a Random set of data and plots it as a bar chart
    // Called once on page load, then each time the button is clicked.
    function change_data() {
        var data = generate_random_data(numberOfBars);
        plot_data(data);
    }
    
    // Generates a Random set of data and plots it as a bar chart
    // Called once on page load, then each time the button is clicked.
    function filtered_data() {
        var data = generate_random_data(numberOfBars);
        data = data.filter(function (d) { return d > get_filter_value(); });
        plot_data(data);
    }
    
    
    function plot_data(data) {
        // Bind the data to the collections of rectangles and text in the svg element
        var bars = svg.selectAll("rect")
                .data(data);
        var labels = svg.selectAll("text")
                .data(data);
        
        // Remove any unneeded rectangles and labels (if new data has less items than the existing chart)
        bars.exit().remove();
        labels.exit().remove();
        // Append any new rectangles and labels that are needed (if new data has more items than existing chart)
        create_bars(bars);
        create_labels(labels);
        // There should now be the right number of rectangles and labels. 
        // Resize and position each one according to the new data items.
        resize_bars(bars, data);
        position_labels(labels, data);        
    }
    function create_bars(bars) {
        bars.enter()
            .append("rect");
    }
    
    function resize_bars(bars, data) {
        bars.transition()
            .duration(500)
            .attr("x", function(d, i) {
                return i * colWidth;
            })
            .attr("y", function(d) {
                return h - d;
            })
            .attr("width", barWidth)
            .attr("height", function(d) {
                return d;
            });
    }    
    
    function create_labels(labels) {
        labels.enter()
            .append("text")
            .attr("text-anchor", "middle")
            .attr("font-family", "sans-serif")
            .attr("font-size", "11px")
            .attr("fill", "white");
    }
    
    function position_labels(labels, data) {
        labels.transition()
            .duration(500)
            .text(function(d) {
                return d;
            })
            .attr("x", function(d, i) {
                return i * colWidth + barWidth / 2;
            })
            .attr("y", function(d) {
                return h - d + 14;
            });
    }
    
    function generate_random_data(n) {
        data = [];
        
        for(i=0; i<n; i++) {
            var value = Math.floor((Math.random() * 500) + 1);
            data.push(value);
        }
        return data;
    }
    
    function get_filter_value() {
        var value = null;
        var x=document.getElementById("filter_value").value;
        value = parseInt(x);
        if(isNaN(value))
            value=100;
        
        return value;
        }
        
    </script>
</body>
</html>