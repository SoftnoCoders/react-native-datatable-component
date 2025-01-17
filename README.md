# react-native-datatable-component
[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger) ![npm](https://img.shields.io/npm/v/react-native-datatable-component) 

A React Native datatable component for dynamically perform actions like display, sorting, select, custom design, delete & touch events.

## Why this Module? 

Not so much complex & unnecessary thing Exists. All those basics functionality which everyone Needs. <br>Everything with clear & simple!

## Preview

<!-- <img src="https://live.staticflickr.com/65535/51349744677_4d8704a8a4_h.jpg"
     alt="Markdown Monster icon"
     style="float: left; margin-right: 10px; width: '20%'" /> -->
     
<!-- ![Demo](https://live.staticflickr.com/65535/51349744677_4d8704a8a4_h.jpg) -->
<img src="https://live.staticflickr.com/65535/51349744677_4e83954287_z.jpg" width="35%"  alt="Demo">


## Installation

As this module depends on nothing means `no dependency require` so, just 1 below step require to install it.

```sh
npm install react-native-datatable-component
```

or

```sh
yarn add react-native-datatable-component
```

## Usage

```js
import DataTable from 'react-native-datatable-component';
```

```js

import React from 'react';
import DataTable, {COL_TYPES} from 'react-native-datatable-component';

const someComponent = props => {
    return (
        <DataTable
            data={[ 
                { name: 'Muhammad Rafeh', age: 21, gender: 'male' },
                { name: 'Muhammad Akif', age: 22, gender: 'male' },
                { name: 'Muhammad Umar', age: 21, gender: 'male' },
                { name: 'Amna Shakeel', age: 22, gender: 'female' },
                { name: 'Muhammad Ammar', age: 20, gender: 'male' },
                { name: 'Muhammad Moiz', age: 13, gender: 'male' }
            ]} // list of objects
            colNames={['name', 'age', 'gender']} //List of Strings
            colSettings={[{ name: 'name', type: COL_TYPES.STRING }, { name: 'age', type: COL_TYPES.INT }, {name: 'gender', type: COL_TYPES.STRING}]}//List of Objects
            noOfPages={2} //number
        />
    );
}

export default someComponent;

```

## Flexibility
You can easily control it's width by wrapping it with View

```js

<View style={{width: '80%', alignSelf: 'center'}}> //margin: 20}
  <DataTable {...props} />
</View>

//All These Properties Works on DataTable from it's parent View
//width, alignSelf, margin, padding

```

## Props

DataTable component accepts following props.

Name | Type| Default | Is Require 
--- | --- | --- | ---
data | [] of {} | - | Yes 
colNames | [] of Strings | - | Yes 
colSettings | [] of {} | - | No
noOfPages | Number | 2 | No
onRowSelect | Func | - | No

## Constants

```js

  import DataTable, {COL_TYPES} from 'react-native-datatable-component';

  // Values
  // COL_TYPES.INT
  // COL_TYPES.STRING
  // COL_TYPES.CHECK_BOX

  //Below You will learn how to use constants while doing colSettings.

```

## Props Explanation

`Data` *List of Objects*

Data must be List of Objects where each object will represent a Row Object's Key will be the Name of Column & value will be your Data.

```js
  
  //List of Objects
  [{ nameOfCol: 'Your Data' }, ...]
  
  //For Example
  data={[ {studentName: 'Akif', age: 19}, {studentName: 'Ammar', age: 20}, ... ]}
  
```
  
> In above case studentName & age is Names of Column & Values are data in that Column.

- Special Objects Key

1. doHighlight

*If you want to highlight Any Row then use this*

```js
  
  {..., doHighlight: 'default'} // To use Component's default Highlight Color
  {..., doHighlight: 'green'} // Any Color Name
  {..., doHighlight: 'rgb(255,233,22)'} // Accepts RGB
  {..., doHighlight: 'rgb(255,233,22, 0.6)'} // Accepts RGBA
  {..., doHighlight: { backgroundColor: 'RGB/HEX/COLOR Name', textColor: 'RGB/HEX/COLOR Name' }} // Pass object if you want to change Text Color.
  
```


`colNames` *List of Strings*

By Default DataTable shows columns which mentions in colNames & pick up Columns Data/Value from the Data prop.

```js
  
  //List of Strings
  ['studentName', 'age']
  
  //Note
  //Data prop have Object keys same/match the strings Above.  
  
```

`colSettings` *List of Objects*

Below is the shape of Objects.

```js

//Object Shape
{
      name: 'name Of Column Here', // String will be the Column Name
      type: COL_TYPES.STRING / COL_TYPES.STRING, // INT || STRING
}
        
```

`noOfPages` *Number*

How Many Pages/Sections You want in DataTable!!!

`onRowSelect` *Function*

DataTable passes full row in Object in which colName's value will change according to check press! 

```js
     
import DataTable, {COL_TYPES} from 'react-native-datatable-component';
    
const someCom = () => {

     //You can pass COL_TYPES.CHECK_BOX Column's value in true/false, by default it will be false means checkBox will be uncheck!
     
     const data = [
           { menu: 'Chicken Biryani', select: false }, //If user select this row then this whole object will return to you with select true in this case
           { menu: 'Chiken koofta', select: true },
           { menu: 'Chicken sharwma', select: false }
     ]
     
     const nameOfCols = ['menu', 'select'];
     
     return(
          <DataTable
               onRowSelect={(row) => {console.log('ROW => ',row)}}
               data={data}
               colNames={nameOfCols}
               colSettings={[{name: 'select', type: COL_TYPES.CHECK_BOX}]}
          />
     )
}

```

## In Development

We are developing the rest of Functionality! Soon we made the release!

## For Future Issues & Contributions

Any one can Contribute & in case of any issue, open the issue Forum!

