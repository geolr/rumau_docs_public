# osdu command

Python package

# Howto

Tips and tricks

## Login, Auth
Need to get correct config file (check github)

Make sure things work towards the server

Test command `osdu status`

`osdu config list` shall be giving the current values

### How to fix token
?

# osdu-cli

Trying to search

## search query -k

`osdu list records` to get all

`osdu search query -k osdu:wks:reference-data--UnitOfMeasure:1.0.0 -ojson --filter results[7].data` => Gives the entire content in "data"-key

`osdu search query -k osdu:wks:reference-data--UnitOfMeasure:1.0.0 -ojson --filter results[7].data.Code` => Gives for the 8th element in the results[] array the value of the data-Code key
* rather pipe to grep?

`osdu search query -k osdu:wks:reference-data--UnitOfMeasure:1.0.0 -ojson --filter results[*].data.IsBaseUnit` => listing of the true or false values
