# Python version

RHEL7: `scl enable rh-python38 bash`

`.bashrc` may contain `source scl_source enable rh-python38`

# Prep

`python3 -m venv osdu-cli-env` where last argument is the name of the environment

Don't forget to Activate the environment: `source osdu-cli-env/bin/activate`

Deactive with: `deactivate`

# Windows

venv on Windows seems to work to activate like this: `.\windows_env\Scripts\activate`

Once in the activate `venv`, then `pip install` just works

Also `python -m jupyterlab` is OK and starts the server and all.

# Help

In interactive commandline: `help(datetime)` to get help for the datetime module, or in any other

# Libs

## Pandas

`pd.concat` needs a `sort=True`

`pd.Series` to create an empty, needs as dtype-specified, default is now `object`

`pd.json_normalize(j, record_path=['data','results'])` where j is dictionary of json, data and results are levels in the json hierarchy

`df.to_csv('new.csv')` for export to csv

## Record linking
"record linkage and deduplication"
Record linkage Toolkit: https://recordlinkage.readthedocs.io

# General

Cheatsheet type of notes

## Loops

`for` loops => need a range of numbers or sequences of items

`while` loops => need a logical expression

* `continue`: jump back to the loop and see if more needs to be done

* `break`: leave the loop immediately

* `pass`: Do nothing
