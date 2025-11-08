Problem. if you want to rename a json property from a column which currently has been serialized and persisted in a database with a particular name. how do you do so whereby the database's existing data can reflect this new name change? 

>>> there are quite a few ways. not all very robust. one way is to manually rename all the existing data in the database to align with your new change. Another way is to use application logic that if it reads the old name it knows to map it to the new name.

This seems like a **problem with database infrastructure itself**. data doesnt seem to be flexible and fluid here. its quite fragile and rigid

actually this may be more of a problem of deciding to store json in a column. because the column wont know what the schema of the json will be, just that you are providing a valid json. therefore it seems that if you were to use json columns you would have to handle the serialization and deseriliazation in application logic given changes to the json schema like property renames and so forth

## One solution is to include a `version` identifier to the json to specify the history of the jsons schemas evolution and therefore can pattern match on the version in order to apply the specific rules to the version

This solves programming yourself into a corner later into the future!
