# CSVtoNestedJSON

A python 2.7.9 project that converts CSV files to nested JSON. 
Files become prettified with objects in objects.

TO USE THE PYTHON FILE

Placec the csv in the same directory as the python script.
Import the script into IDLE.
To make objects etc, add your behaviours etc to a csv file in the first row.
All files become an array of objects by default.
Each csv becomes a seperate object.

Eg.

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

Eg.

    name, details{, year, location, }, boolean
    this, ,1999, Kamchutka, , true
    that, ,1994, Ohio, ,false
    other, ,1998, Werribee, ,true

Becomes 

    [{
      'name': 'this',
      'details':
      {
        'year': 1999,
        'other': 'Kamchutka'
      },
      'boolean': true
    },
    ......
    ......
    ]
