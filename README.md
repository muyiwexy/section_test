Data representation with react and ant design 


For the tutorial we will shiw you how to create constructive charts analysis for your application using ant charts with a focus on how to develop flow charts for your software development projects using data suppliied to ant library framework.

To begin kick start you react project within which you want to represent you data visualizations using the following commands

- npx create-react-app chart-analysis


navigate into the folder

- cd  chart-analysis

- start your project

- npm start


the file displayed when you application start can be found in "src/App.js". The index.js file is the root entry point for all react application and serves the App.js file which holds the first contents we see on our application.

Next we need to install the ant design chart library. The library that will help us develop the charts we need for our analysis

- yarn add antd
- yarn add @ant-design/charts

Since we would be working on flowcharts we need to also impot the flowchart library as well

- yarn add @ant-design/flowchart

Together with 'react-dom' and 'react', antdesign flowchart also relies on 'antd icons', '@ant-design/icons' and 'lodash'. To achieve these we need to install both packages into our application

- yarn add lodash
- yarn add @ant-design/icons

Your package.json in general should have the following files availabe in it
```
"dependencies": {
    "@ant-design/icons": "^4.6.0",
    "antd": "^4.6.3",
    "lodash": "^4.17.20",
    "react": ">=16.8.4",
    "react-dom": ">=16.8.4"
  }
```

Then we head on next to import the library. We can use import or require to start.

First we import the necessary css file by adding the code below to the top of our App.js file

- import "@ant - design/flowchart/dist/index.css";

Then we can now import our flowchart an other charts in the various file we need them as we would do for any other package we wish to use in a regular react application.


We are all set



Flowcharts

for our flowchart we will create a react component in a new file called sampleFlowChart.js. This file will house our flowchart component that will hold the data set for our codes.

```
import React from 'react';
import ReactDOM from 'react-dom';
import { Flowchart } from '@ant-design/charts';

const SampleFlowchart = () => {
  return (
    <>

    </>
  );
};

export default SampleFlowchart;
```

in the code snippet above we are importing react, react-dom and Flowchart from the ant design chart library.
Next we create our SampleFlowChart copmonent and export it as the default using react functional component rrendering mechanism.
```
<div style={{ height: 600 }}>
      <Flowchart
        onSave={(d) => {
          console.log(d, JSON.stringify(d));
        }}
        toolbarPanelProps={{
          position: {
            top: 0,
            left: 0,
            right: 0,
          },
        }}
        scaleToolbarPanelProps={{
          layout: 'horizontal',
          position: {
            right: 0,
            top: -40,
          },
          style: {
            background: 'transparent',
          },
        }}
        canvasProps={{
          position: {
            top: 40,
            left: 0,
            right: 0,
            bottom: 0,
          },
        }}
        nodePanelProps={{
          position: { width: 160, top: 40, bottom: 0, left: 0 },
        }}
        detailPanelProps={{
          position: { width: 200, top: 40, bottom: 0, right: 0 },
        }}
      />
</div>

```
Insrting the code above will display our flowchart dashboard populated with the necessary widgets we need to create a flowchart daigram for any application flow. The widgets present ranges from (parralelogram, to Oval, down to daimond shape for decision making).

Since antd is a chinese based framework some of the text on the interface will be written in chinese, do not be alarmed, there's a way around it. What you can do is to install google translate plugin extension for free in your browser and specify google to translate the website and your good to go with the text transformed to your language of choice.

You can drag widgets from the left panel where there are housed and drop them in the central panel which is the 

Explaining the code snippet

The FlowChart widget creates the panel dashbord that gets displayed on the browser
```
onSave={(d) => {
    console.log(d, JSON.stringify(d));
}}
````
This logs to the console the data set generated from your designs anytime you save your updates. This dataset can be shared to regenerate the flowchart map with anyone.

```
toolbarPanelProps={{
          position: {
            top: 0,
            left: 0,
            right: 0,
  },
}}
```

This sets the position for the top bar of the interface. By changing the values you can chage the position of the top bar. In our application we have set the valu to be house on the top of our application screen
```
scaleToolbarPanelProps={{
          layout: 'horizontal',
          position: {
            right: 0,
            top: -40,
          },
          style: {
            background: 'transparent',
          },
        }}
```
This sets the positioning of the screen fit, fullscreen, zoom in and zoom out features placed on the top right of the screen. by changing the values we can specify where we want its postion to be on the dashboard.
```
canvasProps={{
          position: {
            top: 40,
            left: 0,
            right: 0,
            bottom: 0,
          },
        }}
```
This handles the positioning of the central canvas on the screen where the central canvas layer to hold widgets dropped is displayed.
```
nodePanelProps={{
          position: { width: 160, top: 40, bottom: 0, left: 0 },
        }}
        detailPanelProps={{
          position: { width: 200, top: 40, bottom: 0, right: 0 },
        }}
```
These handles panels on both sides of the screen. THe left panel is handled by the nodepanelprops which houses the nodes and the right is used to specify details about the properties of the widget currently in focus.


There is a default data property of the flowchart widget. This data proporty takes in a value of tye object. This object has two properties, nodes and edges. Both of which are arrays of all the nodes present to be present in the application. The data obtained from the onSaved function call displayed in the interface

Hence the final code will be 

```
import React from 'react';
import ReactDOM from 'react-dom';
import { Flowchart } from '@ant-design/charts';

const SampleFlowchart = () => {
  return (
    <div style={{ height: 600 }}>
      <Flowchart
        onSave={(d) => {
          console.log(d, JSON.stringify(d));
        }}
        toolbarPanelProps={{
          position: {
            top: 0,
            left: 0,
            right: 0,
          },
        }}
        scaleToolbarPanelProps={{
          layout: 'horizontal',
          position: {
            right: 0,
            top: -40,
          },
          style: {
            background: 'transparent',
          },
        }}
        canvasProps={{
          position: {
            top: 40,
            left: 0,
            right: 0,
            bottom: 0,
          },
        }}
        nodePanelProps={{
          position: { width: 160, top: 40, bottom: 0, left: 0 },
        }}
        detailPanelProps={{
          position: { width: 200, top: 40, bottom: 0, right: 0 },
        }}
      />
    </div>
  );
};
export default SampleFlowchart;


```




MultiLine

For our multiline we will create a new file to house it as a component. call the file sampleMultiLine
```
import React, { useState, useEffect } from 'react';
import ReactDOM from 'react-dom';
import { Line } from '@ant-design/charts';

const SampleMultiLine = () => {
  const data = [
    {
      "year": "2010",
      "value": 3107,
      "category": "Cars"
    },
    {
      "year": "2010",
      "value": 3812,
      "category": "Buses"
    },
    {
      "year": "2010",
      "value": 1696,
      "category": "Bikes"
    },
    {
      "year": "2010",
      "value": 446,
      "category": "train"
    },
    {
      "year": "2010",
      "value": 67,
      "category": "Walk"
    },
    {
      "year": "2011",
      "value": 3134,
      "category": "Cars"
    },
    {
      "year": "2011",
      "value": 4055,
      "category": "Buses"
    },
    {
      "year": "2011",
      "value": 1756,
      "category": "Bikes"
    },
    {
      "year": "2011",
      "value": 494,
      "category": "train"
    },
    {
      "year": "2011",
      "value": 64,
      "category": "Walk"
    },
    {
      "year": "2012",
      "value": 3200,
      "category": "Cars"
    },
    {
      "year": "2012",
      "value": 4106,
      "category": "Buses"
    },
    {
      "year": "2012",
      "value": 1783,
      "category": "Bikes"
    },
    {
      "year": "2012",
      "value": 519,
      "category": "train"
    },
    {
      "year": "2012",
      "value": 65,
      "category": "Walk"
    },
    {
      "year": "2013",
      "value": 3220,
      "category": "Cars"
    },
    {
      "year": "2013",
      "value": 4126,
      "category": "Buses"
    },
    {
      "year": "2013",
      "value": 1806,
      "category": "Bikes"
    },
    {
      "year": "2013",
      "value": 554,
      "category": "train"
    },
    {
      "year": "2013",
      "value": 68,
      "category": "Walk"
    },
    {
      "year": "2014",
      "value": 3280,
      "category": "Cars"
    },
    {
      "year": "2014",
      "value": 4117,
      "category": "Buses"
    },
    {
      "year": "2014",
      "value": 1823,
      "category": "Bikes"
    },
    {
      "year": "2014",
      "value": 568,
      "category": "train"
    },
    {
      "year": "2014",
      "value": 68,
      "category": "Walk"
    }
  ];
   
  
  const config = {
    data,
    xField: 'year',
    yField: 'value',
    seriesField: 'category',
    xAxis: {
      type: 'time',
    },
    yAxis: {
      label: {
        formatter: (v) => `${v}`.replace(/\d{1,3}(?=(\d{3})+$)/g, (s) => `${s},`),
      },
    },
  };
  return <Line {...config} />;
};
export default SampleMultiLine;
```

Explainer code.

The code above imports react and react-dom which are both required. Also imported is the antdesign Line provided by the antdesign chart library.
```
const SampleMultiLine = () => {
  return (
      <>
      </>
  );
};
export default SampleMultiLine;
```
We define our component SampleMultiLine and export it as the default component for our file. This is imported and utilized in the App.js file using the snippet below
``
<SampleMultiLine />
```
there are no props so none is passed to it.



We define our data set as an array, for each unique line we have a single element representing its for that particular year.


```
  const config = {
    data,
    xField: 'year',
    yField: 'value',
    seriesField: 'category',
    xAxis: {
      type: 'time',
    },
    yAxis: {
      label: {
        formatter: (v) => `${v}`.replace(/\d{1,3}(?=(\d{3})+$)/g, (s) => `${s},`),
      },
    },
  };
```
The major piece of code is the one that describes the various configuration of out Multiline graph. The configuration variable is an object that takes in the dataset in a "data" property, the xField property takes a value that is a key in our dataset of which we want to be our x-axis data. similarly, the yField property takes a value that is a key in our dataset of which we want to be our y-axis data. 
THe seriesField speciefies the field in our dataset we want to us as our line distiguisher. So for every different/unique value for the proerty "category" in our dataset the chart will create a new line to represent it in the chart.

For the xAxis and yAxis property of our config variable we specify a string to identify what type of value are to be represented there.

With a large dataset that has multiple values a good representation of our multiline chart can be viewed.
