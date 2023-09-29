# Misc

find which shell is in use `echo $shell`

For sourcing: `.cshrc`

For sourcing: `.profile`, `.bash_profile` or `.bashrc`

`mkdir -p some/dir/sub/next/more` create parents as needed

# sed

`sed -i 's/foo/bar/g' *`

sed always does the first match per line, then moves to next line
!!! -i is for --in-place which is changing the actual file. --in-place[=SUFFIX] keeps the original file with SUFFIX in the end of the filename, edits a new file (without SUFFIX)

Testing: sed 's/C1/SGEO_C1/g' <file.las feeds the file.las content to the sed command and outputs to std-out; then do the -i on the actual file

`sed -i 's/C1/SGEO_C1/g' *.las`

`sed -i 's_ \{2,\}\t\t_"&_' *.txt`

finds two or more spaces {2,}, then two tabs \t\t
replaces the match & with a doublequote and the match "&
Can also be included in a shell-script (Git Bash on Windows works nice)

```
#!/bin/bash
# changing strings in many las files in current directory
sed -i 's/C1/SGEO_C1/g' *.las
```
When in need to use a slash /, then use backslash to escape.

had to replace 48_ with GB48/
this seemed to work (Git Bash, Windows): `sed -i 's/48_/GB48\//' *.las`
GB-wells: 2-step

Add blank where a number after minus
`sed -i 's/-[0-9]/-&/' *.txt`
then all the ones that should have minus and space have --, new sed:
`sed -i 's/--/- /' *.txt`

Add to beginning of line `sed -i 's/^/"/' test.txt`

Find first tab, replace with doublequote and tab `sed -i 's_\t_"\t_' file.txt`

# grep 

find a string in files

`grep SOR *.las` look for SOR in all .las files, prints also the line where found

`grep -l SOR *.las` prints only the filename where found

`grep -l SOR *.las | xargs.exe cp -t ./selected_curves/` to copy the found files to a different folder

# file properties
## Time
* `mtime` modification time => `ls -l` shows that
* `ctime` change of a file's metadata such as ownership, location, permissions
* `atime` access time => try `ls -lu`

also find with -atime might help: To find files whose modification time is 2 or more days ago: `find . -type f -mtime 2`

# find

for files and folders/directories

`find` looks recursively from current pwd

`find -type f` is for finding only *files*

`find -type d` is for finding only *directories*

`find -name "*.txt"` looks for patterns in name (glob), case-sensitive

`-iname` would be case-insensitive

`-path` is like name but on the entire path. * will match both / and leading dots in filename

`-ipath` then case-insensitive

Each expression is true or false for the current file. Many those expressions are chained as `-and` per default. `$ find -name "*.js" -type f` would do the and for the name and type file.

`-or` would allow for several tests: `find -name "*.js" -or -name "*.css" -type f`

`-not` to negate expression

paranthesis group expressions, but require escaping in bash.

`-exec` to do something with the results

# regex

Regular expressions

<https://github.com/google/re2/blob/main/doc/syntax.txt>

# rsync

`-az` archive and compress is good

`-n`  for dry-run

`--exclude attic/` to omit some parts

`--bwlimit=300` limit the bandwidth used

trailing slash (/) on the source directory:
* If you do __not__ use a trailing slash, the source directory is copied to the destination directory, and then the contents of the directory.
* When you __do use__ the trailing slash, rsync only copies the content of the source without creating an additional directory level.

# du
Disk usage

`du -h` to get human-readable size (like Megabyte, GB when appropriate), will traverse recursively into subdirectories and have one line per file

`du -hs` just output one summarized line with the total if the argument was a folder

`du -hs BH21E_HA_30*` seems to work:
```
6.0T	BH21E_HA_300
90G	BH21E_HA_301
1.6G	BH21E_HA_302
```

# cli
Environment variables: `printenv` display all 

vs. Shell variables: Environment variables visible to all processes, not only shell

`VAR="hello"  # shell variable created
export VAR   # variable now part of the environment`

# aliases

`alias newname='command'`

ncdu, not to quit with q only: `alias ncdu='ncdu --confirm-quit'`

------------------------------------------------------------

`blocl 
of 
code
` => Ctrl-e in the browser editor

`uniq` for uniqueness...
