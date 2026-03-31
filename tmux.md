# Learn tmux

Can keep ssh 


## my config
symlinked .tmux.conf to ~/.config/tmux/tmux.con

Copy mode: to avoid [ => `Ctrl-b å` to enter copy mode

Paste in copy mode: to avoid ] => `Ctrl-b ¨` to paste tmux buffer in copy mode (no dead-key?)

## how to

**PREFIX** key combo: Default is `Ctrl - b`, works for me (often recommended to use Ctrl+a instead)

Detach from session: `Ctrl + a, then d`

Attach to session: `tmux attach -t mysession` or `tmux a`

List sessions: `tmux ls` (also from the inside)

Split vertically: `Ctrl + a, then %`

Split horizontally: `Ctrl + a, then "`

Move between panes: `Ctrl + a, then arrow key` or by mouse-click since mouse mode is on

Remove split: `Ctrl + d`, terminates the panes shell process, or `exit`

Keyboard commands `prefix + ?`

### Copy Mode
No interaction with the shell process any more.

needed for:

Scrolling => Mouse wheel, as I have `set -g mouse on` (?)

`å and ¨` for entering Copy Mode and pasting tmux buffer

Leave Copy Mode: `q`

Only `PageUp` can be used to scroll up and stay in Copy Mode, use `q` to leave copy mode

## remote
commands run in tmux, not the ssh session.

A disconnect leaves tmux running and the shell(s) therein. 
Ready to reconnect later.

`ssh user@host` login first, then `tmux new -s sessionname`

**Detach** session `Ctrl+a d` or from inside tmux `tmux detach` => gives back the normal shell on remote machine, then exit so close ssh-session.

Once again logged in to remote host: `tmux attach -t sessionname` or `tmux a`
