# Github writing, Markdown
https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax

https://www.markdowntools.io/github-markdown-cheat-sheet

# json

`"key":"value"` where key is a string

`{}` curly brackets indicate an *object*
=> becomes a `dict` in python

`[]` square brackets indicate an *array* of values 
=> becomes a list or tuple in python
==> can become the value of a key

`null` in json is made `None` in python

Visual Studio Code has a *beautify* option in command palette for readability.


# Database

Denormalized => combining several tables into one (for easier consumption by users)

Normalized would be the data in it's seperate tables

# Excel

<kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>;</kbd> (semi-colon) inserts static string with current *date*

<kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>.</kbd> (dot) inserts static string with current *time*

Both date and time: Do <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>;</kbd> then <kbd>Space</kbd> then <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>.</kbd>

# Harddisks, storage

`shred`, `hdparm`, `dd`, `wipefs` to cleanse old disks?

`DBAN` USB distro for this

wipefs is only on partitions, dd can write zeros
