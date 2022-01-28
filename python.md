# Python version

RHEL7: `scl enable rh-python38 bash`

`.bashrc` may contain `source scl_source enable rh-python38`

# Prep

`python3 -m venv osdu-cli-env` where last is the name of the environment

Don't forget to Activate the environment: `source osdu-cli-env/bin/activate`

# Help

In interactive commandline: `help(datetime)` to get help for the datetime module, or in any other
