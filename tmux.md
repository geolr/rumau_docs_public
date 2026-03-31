# Learn tmux

Can keep ssh 


## my config
symlinked .tmux.conf to ~/.config/tmux/tmux.con

Copy mode: to avoid [ => `Ctrl-b å` to enter copy mode

Paste in copy mode: to avoid ] => `Ctrl-b ¨` to paste tmux buffer in copy mode (no dead-key?)

## how to

**PREFIX** key combo: Default is `Ctrl - b`, works for me

Did not work to change my keyboard to `Ctrl-a` for the **prefix**

Detach from session: `Ctrl + a, then d`

Attach to session: `tmux attach -t mysession` or `tmux a`

List sessions: `tmux ls` (also from the inside)

Split vertically: `Ctrl + a, then %`

Split horizontally: `Ctrl + a, then "`

Move between panes: `Ctrl + a, then arrow key` or by mouse-click since mouse mode is on

Remove split: `Ctrl + d`, terminates the panes shell process, or `exit`

Keyboard commands `prefix + ?`

**Copy Mode**
No interaction with the shell process any more.

needed for:

Scrolling => Mouse wheel, as I have `set -g mouse on` (?)

