# Python version

RHEL7: `scl enable rh-python38 bash`

`.bashrc` may contain `source scl_source enable rh-python38`

# Prep

`python3 -m venv osdu-cli-env` where last argument is the name of the environment

Don't forget to Activate the environment: `source osdu-cli-env/bin/activate`

Deactive with: `deactivate`

# Help

In interactive commandline: `help(datetime)` to get help for the datetime module, or in any other

# Libs

## Pandas

`pd.concat` needs a `sort=True`

`pd.Series` to create an empty, needs as dtype-specified, default is now `object`

## Record linking
"record linkage and deduplication"
Record linkage Toolkit: https://recordlinkage.readthedocs.io
