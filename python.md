# Python version

RHEL7: `scl enable rh-python38 bash`

`.bashrc` may contain `source scl_source enable rh-python38`

# Prep

`python3 -m venv osdu-cli-env` where last argument is the name of the environment

Don't forget to Activate the environment: `source osdu-cli-env/bin/activate`

Deactive with: `deactivate`

# Package Management with uv
> uv is a next-generation package manager for Python that delivers exceptional speed and modern dependency management. It is designed to be a drop-in replacement for pip, pip-tools, and virtualenv, providing a significantly faster and more reliable experience.
https://betterstack.com/community/guides/scaling-python/uv-explained/

Can handle the Python-versions for you

`Windows Terminal` as app from AppStore

`winget`  for install, then creating on a `project` with uv

`uv run hello.py` to run a script

`uv run odsu -h` for this tool (not sure if `uv add osducli` is required or not)

`uv run --with jupyter jupyter lab` to run jupyterlab without installing it in project virtual env. Dependencies will be loaded via `import...` from local virtual env.

# Windows

(WinExpl `Shift+Rightclick` for PowerShell in current folder)

In PowerShell, the command for running python to create venv:
` & 'C:\Program Files\Pythonnnn\python.exe' -m venv windows_env`

venv on Windows seems to work to activate like this: `.\windows_env\Scripts\activate`

Once in the activate `venv`, then `pip install` just works

Try `C:\path\rumau_dev\welllogs_venv>C:\path\rumau_dev\welllogs_venv\Scripts\python.exe -m pip install --upgrade pip`

Try `C:\path\rumau_dev\welllogs_venv>C:\path\rumau_dev\welllogs_venv\Scripts\python.exe -m pip install tqdm`

List all installed packages `python.exe -m pip list`

Also `python -m jupyterlab` is OK and starts the server and all.

# Help

In interactive commandline: `help(datetime)` to get help for the datetime module, or in any other

# Libs

List all installed packages `python -m pip list`

Update: ?

Only pip upgrade: `python pip install --upgrade pip`

## Record linking
"record linkage and deduplication"
Record linkage Toolkit: https://recordlinkage.readthedocs.io

# General

Cheatsheet type of notes

## Strings

`r"C:\folder"` this is a raw string literal to avoid the double `\\`; literal backslash (as opposed to escape character in a normal string)

may want to learn about `formatted string literals` or f-strings

`f"sometext{variable} more text {another-variable}

Make a timestamp: 
```python
from datetime import datetime   #for timestamp in filename</code>
datetime.now().strftime("%Y-%m-%d_%a_%H%M%S")
```

## Pathlib

to get a string from a Path-object:
```python
>>> from pathlib import Path
>>> str(Path(r"C:\Users\rm\realpython\file.txt"))
'C:\\Users\\rm\\realpython\\file.txt'
```

Recursive listing, content of subfolders:
```python
# .rglob() for recursive listing

diskspace = 0

for f in p.rglob("*"):
    if f.is_dir():
        print(f, "total so far ", diskspace)
    else:
        #print(f)
        s = f.stat().st_size
        #print(type(s))
        diskspace += s
        print(f,s,"total so far:",diskspace)
print(diskspace)
```


## Loops

`for` loops => need a range of numbers or sequences of items

`while` loops => need a logical expression

* `continue`: jump back to the loop and see if more needs to be done

* `break`: leave the loop immediately

* `pass`: Do nothing

##  Tuples

immutable, comparable, sortable( see more[https://www.py4e.com/html3/10-tuples py4e.com])
```python
 >>> t = ('a', 'b', 'c', 'd', 'e')
 >>> print(t[1:3])
 ('b', 'c')
```
Using the constructor to create a tuple (thus don't use this as variable name, it's already the constructor name)
```python
 >>> t = tuple('lupins')
 >>> print(t)
 ('l', 'u', 'p', 'i', 'n', 's')
```

Modify the elements of a tuple by replacing:
```python
 >>> t = ('A',) + t[1:]
 >>> print(t)
 ('A', 'b', 'c', 'd', 'e')
```
