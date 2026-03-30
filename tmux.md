# Learn tmux

Can keep ssh 


**PREFIX** key combo: Default is `Ctrl - b`, works for me

Did not work to change my keyboard to `Ctrl-a` for the **prefix**

Detach from session: `Ctrl + a, then d`

Attach to session: `tmux attach -t mysession` or `tmux a`

List sessions: `tmux ls` (also from the inside)

Split vertically: `Ctrl + a, then %`

Split horizontally: `Ctrl + a, then "`

Move between panes: `Ctrl + a, then arrow key`

Keyboard commands `prefix + ?`

**Copy Mode**
needed for:

Scrolling => Mouse wheel, as I have `set -g mouse on` (?)
