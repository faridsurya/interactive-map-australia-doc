# Interactive Map of Australia with Charts and Markers

This interactive map will help you to present data on web pages without requiring more knowledge about programming. You only need to write your data in JSON format and you already have a web page that represents your data on maps and charts.
 
## Features
- Selectable vector map
- Customize vector map styles
- Display charts related with selected area
- Display multi charts with multi chart type
- Display markers based on geolocation with your own marker image
- Visibility setting of markers and map tile
- Display your pages in markdown format



## Demo

See Live Demo [here](http://demos.sunhouse.co.id/aus/) and get it in [envato market](https://codecanyon.net/item/interactive-map-of-australia-with-charts-markers-and-pages/27239425)

## Installation

For local installation on your computer, you only need to run the server in the folder to execute the index.html file. For example, you can use php-cli by running the command:
 
```php -S localhost: 3000```
 
Go to your browser and access to the address http: // localhost: 3000 to run the application. Make sure you are connected to the internet.
 
You can also run the application using XAMPP. Make a folder on htdoc, for example with the name 'mymap'. Move all application files into the mymap folder and then access to the address http: // localhost / mymap. Make sure XAMPP is running.
 
For global installation, you just need to put all the files in the folder into your hosting folder.
 
## File Structure

Folder contain the files:
```
- index.html
+ assets
    - data.json
    - config.json
    - markers.json
    - pages.json
    + markers
      - dot.svg
    + pages
      - mypages.md
- and other js files
```

**DO NOT REMOVE those files!**
 
## Add Charts Data

Data charts are taken from the data.json file. The data structure in the file is:
```
[
    {
        "stateCode":"1",
        "stateName":"New South Wales",
        "charts":[
            {
                "title":"Column Chart",
                "type":"ColumnChart",
                "columns":["Country", "Value 1", "Value 2"],
                "data":[
                    ["London", 8136000, 678000],
                    ["New York", 8538000, 890200],
                    ["Paris", 2244000,345000],
                    ["Berlin", 3470000, 7891000],
                    ["Kairo", 19500000, 3456999]
                  ]
            },
...
]
},
...
]
```
 
You can add data by modifying the chart attributes. The required variables are:
 
**title:**
Title of your charts
 
**type:**
Type of your chart. Charts library is using Google Charts. You can refer to the chart type of the library. You can get the charts gallery here.
 
**columns:**
Column name of data. Column length data and data item must be the same. For example, if column data is `[“Country”, “Value 1”, “Value 2”]` then the each item of data must have 3 items.
 
**data:**
Data content that will present in charts. The structure of each item is `[“label”, value1, value2]`. The label must be string and the value must be integer or double.
 
**DO NOT modify the stateCode and stateName attributes.**
 
## Add Markers Data
 
You can add the markers into the map with your own image marker and title. To add the marker, please modify the markers.json file. Structure of the file is:

```
[
    {
        "lon": 115.8604796,
        "lat":-31.9527121,
        "src":"markers/dot.svg",
        "text":""
    },
    {
        "lon":130.30,
        "lat":-24.847,
        "src":"markers/dot.svg",
        "text":""
    }
]
```
 
**lon:**
Longitude coordinate position. You can get that value from google maps or openstreetmap.
 
**lat:**
Latitude coordinate position.
 
**src:**
Marker image location. Place your marker image in the markers folder. You can use the .svg, .jpg, or .png image.
 
**text:**
Text of your marker.

## Change Title, Style, and Visibility

You can change the title, style, and visibility by modifying the config.json file. The contain of config.json file is:

```
{
    "title":"AUSTRALIA",
    "navbarColor":"primary",
    "map":{
        "fill":"rgba(255, 0, 0, 0.2)",
        "stroke":{
            "color":"white",
            "widht":2
        }
    },
    "selectedMap":{
        "fill":"rgba(255, 0, 0, 0.6)",
        "stroke":{
            "color":"green",
            "widht":2
        }
    },
    "showMapTile":true,
    "showMarkers":true
}
```
 
**title:**
Title of your application. Title will appear in the navigation bar.
 
**navbarColor:**
You can modify the color of the navigation bar. The options of color are: primary, default, warn.
 
**map.fill:**
Color of default map overlay. You can use hex color system (“#ccc”) or rgba color system.
 
**map.stroke:**
Stroke style of default vector map.
 
**selectedMap:**
The style of the selected map.
 
**showMapTile:**
If true, a global map will appear. Set the value false If you want to hide the global map.
 
**showMarkers:**
True value will make the markers appear on the map.
 
## Create Page

You can add your own page in markdown format. To create your own page, follow the steps:
1. Modify the pages.json file. Add new object in the array:

```
[
    {
        "title":"My Page",
        "src":"./assets/pages/mypage.md"
    }
]
```
 
The code above will get a markdown file that is placed in the assets/pages folder. The title ‘My Page’ will appear in the navigation bar.
 
2. Place your markdown file in folder assets/pages/.

