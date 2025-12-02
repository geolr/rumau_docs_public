# Misc

find which shell is in use `echo $shell`

For sourcing: `.cshrc`

For sourcing: `.profile`, `.bash_profile` or `.bashrc`

`mkdir -p some/dir/sub/next/more` create parents as needed

What does * mean after filename in a ls -l listing
Can't delete even when owned by me and 755 access?

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

# ls

Oldest in the bottom: `ls -lt`

Give the matching directories only using the `-d` switch:  `ls -ld /somepath/dirname-A*/` shows only the foldernames matching, not their content (I think this approach is called shell globbing)

# find

for files and folders/directories

`find` looks recursively from current pwd

- or the given path `find <pathtosearch> <options like name...>`
- can also be several paths in a space-delimited list `find <pathtosearch> <anotherpath> <options like name...>`

`find -type f` is for finding only *files*

`find -type d` is for finding only *directories*

`find -name "*.txt"` looks for patterns in name (glob), case-sensitive
==> without the quotes (not sure difference single vs. double) the shell would attempt to interpret *.txt

`-iname` would be case-insensitive

`-path` is like name but on the entire path. * will match both / and leading dots in filename

`-ipath` then case-insensitive

Each expression is true or false for the current file. Many those expressions are chained as `-and` per default. `$ find -name "*.js" -type f` would do the and for the name and type file.

`-or` would allow for several tests: `find -name "*.js" -or -name "*.css" -type f`

`-not` to negate expression

paranthesis group expressions, but require escaping in bash.

`-exec` to do something with the results

`2>/dev/null` to direct stderr to nowhere, thus not shown in terminal any more (e.g. access denied messages)

`-ls` is an option to show results (see man for sizes 1K usually)

nicer maybe: `find ./BH21E_HA_40* -name "*_1445*" | xargs ls -lh` then with human-readable sizes (more examples online for tricky cases)

Look for recent files:
`find /path/to/directory -type f -printf '%T@ %p\n' | sort -n | tail -n 20`

`%T@` is seconds since the epoch, I guess this would sort properly.

Then a `ls -l` on dir would allow to check more

__Examples for `find`:__

Find a specific filename in only some of the present directories `find ./BH2* -name somefile.ext`

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

`du -h -d1` will summarize for the folders at folder-depth = 1

`du -hs BH21E_HA_30*` seems to work:
```
6.0T	BH21E_HA_300
90G	BH21E_HA_301
1.6G	BH21E_HA_302
```

Chatbot suggested to find size of certain directories `find /path -maxdepth 1 -type d -name 'dirname-A*' -exec du -sh {} \;`

Explanation:
`find /path`: This searches in the specified path.  
`-maxdepth N`: Replace N with the maximum number of directory levels to descend into. For example, -maxdepth 1 restricts the search to the specified directory only, while -maxdepth 2 includes one level of subdirectories.
`-type d`: This restricts the search to directories.  
`-name 'dirname-A*'`: This matches directories that start with dirname-A.  
`-exec du -sh {}`: This executes the du command on each found directory:  
`du`: Disk usage command.  
`-s`: Summarizes the total size of each argument.  
`-h`: Human-readable format (e.g., KB, MB).  
`{}`: A placeholder for the current directory found by find.  
`\;`: This signifies the end of the -exec command.  

try also `2>/dev/null` to direct stderr to nowhere, thus not shown in terminal any more (e.g. access denied messages)

# ncdu
`--confirm-quit` prevents from unintentional close when hitting Esc too often

`ncdu -e -o outfile.ncdu /some/path`
=> can become quite large
=> -e for extended info, like Last Modified

=> open that saved file again: -f
`ncdu -e -f outfile.ncdu`

=> use `i` to display more on the current file

shows top right corner that a file is open

# cli
Environment variables: `printenv` display all 

vs. Shell variables: Environment variables visible to all processes, not only shell

`VAR="hello"  # shell variable created
export VAR   # variable now part of the environment`

# aliases

`alias newname='command'`

ncdu, not to quit with q only: `alias ncdu='ncdu --confirm-quit'`


# Users and Groups

`id username` shows numerical ids for user and groups

`id -nu <number>` shows the user to the numerical id

`getent group <somename>` shows the members of that group

`getent passwd alfni <somename>` shows info on that user

------------------------------------------------------------

`blocl 
of 
code
` => Ctrl-e in the browser editor

`uniq` for uniqueness...
