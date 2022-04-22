# json

`"key":"value"` where key is a string

`{}` curly brackets indicate an *object*
=> becomes a `dict` in python

`[]` square brackets indicate an *array* of values 
=> becomes a list or tuple in python
==> can become the value of a key

`null` in json is made `None` in python

Visual Studio Code has a *beautify* option in command palette for readability.

# osdu-cli

Trying to search

## search query -k

`osdu list records` to get all

`osdu search query -k osdu:wks:reference-data--UnitOfMeasure:1.0.0 -ojson --filter results[7].data` => Gives the entire content in "data"-key

`osdu search query -k osdu:wks:reference-data--UnitOfMeasure:1.0.0 -ojson --filter results[7].data.Code` => Gives for the 8th element in the results[] array the value of the data-Code key
* rather pipe to grep?

`osdu search query -k osdu:wks:reference-data--UnitOfMeasure:1.0.0 -ojson --filter results[*].data.IsBaseUnit` => listing of the true or false values


# Database

Denormalized => combining several tables into one (for easier consumption by users)

Normalized would be the data in it's seperate tables
