# CSVtoNestedJSON

A python project that converts CSV files to JSON. With objects in objects, arrays in objects, etc

To use this, add your behaviours etc to a csv file in the first row.

All files become an array of objects by default.
Each csv becomes a seperate object.
The output JSON file is also prettified, so you can read it.

Eg

name, year, location, boolean

this, 1999, Kamchutka, heaps

that, 1994, Ohio, notMuch

other, 1998, Werribee, notYourBusiness

Becomes 

[{

  'name': 'this',
  
  'year': 1999,
  
  'other': 'Kamchutka',
  
  'whatUp': true
  
},

......

......

]

If you want an object inside the object, add {} to your CSV file header.
The opening { must have a word in front, and all {} brackets must be in their own columns.

Eg

name, details{, year, location, }, boolean

this, ,1999, Kamchutka, , true

that, ,1994, Ohio, ,false

other, ,1998, Werribee, ,true

Becomes 

[{

  'name': 'this',
  
  'details':{
  
    'year': 1999,
    
    'other': 'Kamchutka'
    
  },
  
  'boolean': true
  
},

......

......

]

TO DO - add the same behaviours for arrays.
