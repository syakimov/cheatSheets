<tmux> = ctrl - b

* Split
    vertically      <tmux> - v
    horizontally    <tmux> - s

* Movement -> save as vim

* Create new tmux tab
    <tmux> - c

* Move between tmux tabs
    <tmux> - l      -> switch between last two tabs
    <tmux> - number -> switch to tab with number

* Working with running log
    scroller does not work  -> forget the mouse
      start navigating mode -> <tmux> - [
        navigate                -> vim keys
        start selecting         -> space
        exit and copy selection -> enter
    paste                   -> <tmux> - ]

* Toggle maximize current screen
    <tmux> - z

* Resize pane
  <tmux> :resize-p -D 15

* Create new session with name
  <tmux> new -s name

* Detach from session
  <tmux> d

* Attach to session 
  <tmux> a -t name

* List all sessions
  `tmux ls`

* Kill current pane/buffer/window/whatever_you_call_it
  `<tmux x`

copy pasted some stuff in order to have them by me
tmux cheatsheet
As configured in my dotfiles.

start new:

tmux
start new with session name:

tmux new -s myname
attach:

tmux a  #  (or at, or attach)
attach to named:

tmux a -t myname
list sessions:

tmux ls
kill session:

tmux kill-session -t myname
In tmux, hit the prefix ctrl+b and then:

Sessions
:new<CR>  new session
s  list sessions
$  name session
Windows (tabs)
c           new window
,           name window
w           list windows
f           find window
&           kill window
.           move window - prompted for a new number
:movew<CR>  move window to the next unused number
Panes (splits)
%  horizontal split
"  vertical split

o  swap panes
q  show pane numbers
x  kill pane
⍽  space - toggle between layouts
Window/pane surgery
:joinp -s :2<CR>  move window 2 into a new pane in the current window
:joinp -t :1<CR>  move the current pane into a new pane in window 1
Move window to pane
How to reorder windows
Misc
d  detach
t  big clock
?  list shortcuts
:  prompt
Resources:

cheat sheet
Notes:

You can cmd+click URLs to open in iTerm.
TODO:

Conf copy mode to use system clipboard. See PragProg book.
