

# git (just local)

`git add file.txt` is *staging* the changes on a file for later commit.

`git commit -m "why this change was done"` commiting the changes together with an explanation

# Send to remote

> login first, if wishing to use cli git, Personal Access Token, Check github-settings-Developer Options-Personal Access tokens (home)

to push local commits to remote:
?`git push origin main`

`git push  <REMOTENAME> <BRANCHNAME>`

# Get from remote

`git pull origin main` is a combination of `fetch` and `merge` (get the changes from remote and combine with own changes), will also get new files from remote

# Github

* Watch: https://github.com/trending
* Star: https://github.com/geolr?tab=stars

## Example pull request, dlisio, correction of link

Readme.md contains dead link, I found an update.

Workflow only in the browser

1. Fork repo
2. edit readme.md in my forked repo ("Submitting a change will write it to a new branch in your fork geolr/dlisio, so you can send a pull request.")
3. commit to my own fork; as suggested by github (asks to directly create a pull request)
4. send pull request, such that my change can be accepted and merged into original source project

## Visual Studio Code and Github

`pull` is a good idea.

Make changes to a file, then save.

Now, a plus-icon next to file in source tab should appear. To *stage* the changes click Plus-icon

Add message near top and click tickmark to *commit*

Once done with local commits: Icon near top to *push* to remote (the button is a push, pull combo)

https://www.youtube.com/watch?v=aUhl3B6ZweQ
