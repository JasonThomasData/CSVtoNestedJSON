# CSVtoNestedJSON

A python 2.7.9 project that converts CSV files to nested JSON. 
Files become prettified with objects in objects.

TO USE THE PYTHON FILE

Place the csv in the same directory as the python script.
Import the script into IDLE.
To make objects etc, add your behaviours etc to a csv file in the first row.
All files become an array of objects by default, but the curly brackets must be placed at first and last columns.
Each csv becomes a seperate object.

Eg.

    {,name, year, location, boolean,}
    ,this, 1999, Kamchutka, TRUE,
    ,that, 1994, Ohio, FALSE,
    ,other, 1998, Werribee, TRUE,

Becomes 

    [
        {
        'name': 'this',
        'year': 1999,
        'other': 'Kamchutka',
        'boolean': true
        },
        ......
        ......
    ]

If you want an object inside the object, add {} to your CSV file header.
The opening { must have a word in front, and all {} brackets must be in their own columns.

Eg.

    {,FirstName,LastName,Age,Circumstances{,What,Why”sit,When{,latitude,},longitude,},}
    ,Joana,Dol”son,39,,TRUE,12,,123,,322,,
    ,James,Bond,29,,FALSE,21,,32,,322,,
    ,Harry,Potter,28,,true,12,,123,,2,,


Becomes 

    [    
        {
            "FirstName" : "Joana",
            "LastName" : "Dol'son",
            "Age" : 39,
            "Circumstances" : 
            {
                "What" : true,
                "Why'sit" : 12,
                "When" : 
                {
                    "latitude" : 123
                },
                "longitude" : 322
            }
        },
        ......
        ......
    ]
