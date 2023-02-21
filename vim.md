# Vim notes

## Navigation

`G` last line

`gg` first line

`42G` move to line 42

## Edit, Copy-Paste

`cw` change current word, removes current word and changes to Insert mode

`yy` copy current line

`p` paste after; `P` paste before

`:reg` shows current content of registers

Paste from register 5: `"5p`

## Delete

`dd` delete entire line

Delete line match a pattern: `:g/profile/d` (/ can be _ if forward slash is needed in pattern)\
\:g as in global

d is the command to be done, here d for line deleteTo *negate*, thus *not* matching search `:g!/pattern/d` will remove all lines not containing pattern

`:g"NO \d\d\dd` Deletes all lines containing the string `"NO nnn` where nnn would be three digits (using _ as delimiter between parts of the command, standard is forward slash /)

`:g/"NO 6[3-8]/d` (to remove all lines for Norwegian Sea wells) => regex way to say numbers from 3 to 8

Delete empty lines:
- `:g/^$/d` for lines containing nothing
- `:g/^\s*$/d` for lines containing only whitespace

## View

`Ctrl+w v` => vertical split (also via :vsplit or :vsp datei.txt)

`\:q` => close this area :qa quit all

`\:e` to open files

`Ctrl+w` arrowkey from hjkl => moves between splits, also `Ctrl+w w`

`Ctrl+w x` => exchange windows

`Ctrl+w r` => rotate or change the content of splits, use R for opposite direction

`\:resize -5` => reduce the size of the split, number of RowColumn

`\:help Ctrl-w`

## Show

`:set number` show line numbers

`:set nonumber` hide line numbers

## Search

`:/searchstring`

`:?GB 204/20a` works for searching string containing `/`\
=> Because `?` is searching backwards from current position, then forward-slashes do not need escaping

`%` is a range: Every line, anywhere in document\
the range `4,7` would be lines four to seven

## Replace

`:s` as in `:substitute` (or Search?) ((in selected Block??))

In current line: `:s/pattern/replace/`, add `g` for all occurences on the line

In whole file: `:%s/pattern/replace/`\
But: Only once per line, Repeat and it will take the next occurrence...\
Add to the end of the command `g` to do it globally\
Add `i` to the end of the command => search case insensitive (`I` forces case-sensitive)

`%s_GB 16/23-4_GB 16/23- 4_g` the slash is part of the search/replace string

**Norwegian characters** Several combined (my Windows-Vim has issues with the characters, but Linux-RGS works well: `:%s/Ø/OE/g | %s/Å/AA/g | %s/Æ/AE/g`

`:%s/Ø/OE/g | %s/Å/AA/g | %s/Æ/AE/g | %s/ø/oe/g | %s/å/aa/g | %s/æ/ae/g`But does this stop processing if a character is not found?

`:%s/\t/"\t/` **replaces** the first Tab on every line with "`<Tab>` => to encapsulate a well name with double quotes

In a terminal: `sed -i 's/C1/SGEO_C1/g' *.las`

## Sorting

This is Fast!

`:sort`

For numeric sort: `:sort n`

## Block Mode (Visual mode)

`Ctrl+v` startet Block/Visual mode

Move commands => selectiert Danach d løscht

Zum Blockweise Kommentieren Cursor am Zeilenanfang Ctrl+v, j soviele Zeilen wie nøtig I Tippen des Kommentars z.B. #### ESC macht die Bearbeitung schnell auch bei grossen Dateien

<http://vimdoc.sourceforge.net/htmldoc/visual.html##blockwise-operators>

`gv` bring back last visual selection

## Other edit commands

```
:%norm A'
   %       = for every line
   norm    = type the following commands
   A'      = append ' to the end of current line
```

## Commands in vim

From within Normal-mode, typing : tells vim that now it's in **Command-mode** if then an i is typed, it won't go to Insert-mode as usual. Command-Mode: Kommand wird gesendet wenn Enter gedrueckt wird `(<CR>)`

\:set showcmd das zeigt an welche tasten gedrueckt wurden

Line numbers: Hide: `:set nonumber`

`Ctrl+g` show current filename

`:echo expand('%:p')` full path of current file

Command mode: `1`, then`Ctrl+g` to show path of current file in statusline

Whitespace: `:set list` switch off by: `:set nolist`

Vergleichen, vom terminal: `vimdiff file1.txt file2.txt` \
`:qa` schliesst alles

## Files

`:w other_filename.txt` writes the current buffer to a new file, keeps current file open in the buffer

`:sav or :saveas other_filename.txt` writes other_filename.txt then hides the current buffer and loads other_filename.txt ready for edits

## Configuration

vimrc

set path+=\*\* += haengt an \*\* dann sind alle Unterverzeichnisse rekursiv dabei

Zum Anzeigen der aktuellen Variablen, in vim, für 'path' :set path?

## Testen/Lernen

* [ ] File-Browser mit: `:tabnew` .
* [ ] norm-Kommando

### Sites

**[theFrugalComputerGuy.com](https://theFrugalComputerGuy.com)**
