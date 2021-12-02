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