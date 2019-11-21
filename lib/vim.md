* Installation
    packages needed for vim:
      Neobundle       => package manager
      silversearch ag => search fast in text
    // recommended
    ln -s dotfiles/.vimrc .vimrc => create a symlinc from repo to ~/.vimrc

  Insert Mode = `IM`

* If you want to completely remove the mouse, you need to use marks.
  Marks can be global and local and you can jump to them when needed.

  create local mark: `m - {lowercase <letter>}` -> `m - <letter>`
  create global mark: `m - {capital <letter>}` -> `m - <letter>`

  go to mark: `' <letter>`

* Tabulation
  move one tab <-|->: `shift - <` and `shift - >`
  auto format: select (V) then = (this requires vim customization)

* Join rows: `J`

* Paste without tabulation problems
  `IM - F2` then `ctrl - V`

* Paste in insert mode what you have yanked
  `IM` - `ctrl - r` - `"`
  `IM` - `ctrl - r` - {register} -> pattern

* Comment text: select then `space - c - c`

* Split vertical `space - v`

* Use `ctrl - hjkl` to navigate in panes

* Search current word
    upward:   `#`
    downward: `*`
  move to:
    previous hit: `n`
    next hit:     `N`

* Search in current file: `/` - text (case sensitive)
* Search globally: `:Ack` - {string pattern}
    this will open a new buffer with all matches
    example: `:Ask "Search"`

* Move to
    previous location => `ctrl - o`
    next location     => `ctrl - i`

* Run syntax checker ex.: eslint
    write file
    `space - j - s`

* Work with git (open fugitive window)
    space - k - s
      `U` => co selected file

* Toggle line numbers
    `space - j - n`

* Move background - foreground
    `ctrl - z`       -> leave in bg
    `fg` in terminal -> start vim again

* Working with directory
    `-`  -> shoes the current directory
      also goes one dir above if in dir-mode

* File fuzzy search
    `ctrl - p`

* Open and save file
    :w {file name} => save with this name
    :e {path to file} => opens file

* Use `p` to match paragraphs

* Use `%` to move to closing/opening bracket

* Pipe stdin -> `cmd | vim -`

* Make vim copy and paste in clipboard
   install vim-gtk -> graphic toolkit
   copy:  "+y
   paste: "+p

* From navigation use `p` for quick review

* Open in a separate buffer `ctrl - w T`

* Change horizontal to vertical git diff `ctrl - w H`

* HML -> High Medium Low -> move cursor without losing focus

* :ls -> Lists all open buffers you can `buffer delete`

* q: -> open history commands in buffer

* `t` just like `f` but skip the matched char

* `<C-x> - s` -> opens spell check in insert mode

* viW -> select everything from space to space

* gv -> selects the last visual selection

* o in visual mode -> jumps to the other end of the selection

* zz -> centers the screen in normal mode

* `<C-r><C-w>` yanks word under cursor in Ex mode

* `m jumps to mark on the exact column

* `vif` and `vaf` select all in function

* `Sexplore` and `Vexplore` open file explorer in new tab

* `<C-g>` shows file status

* `W` and `B` regards words the text separated with spaces

* `;` repeats last search while `,` goes one search back

* `daw` deletes a word with the leading space

* `ib` is alias for `i(` or _inside parentheses

* `iB` is alias for `i{` or _inside braces

* '`.' is the location of the last change same effect as u<C-r>

* `g;` and `g,` traverse backwards for jumps in file

* `:reg` cmd shows all the current registers. `:reg 0` shows only register 0.

* `"+` this register is responsible for the system 'clipboard'

* `"/` keeps the last search

* `":` keeps the last command

* `"%` keeps the relative current file name

* `"#` keeps the alternative file name

* `".` keeps the last inserted text. <C-r>. in insert mode could be useful.

* `"*` this text will be yanked on scroll click. It is populated by the system

* `"=` used for calculating result: `"=4+4<CR>p` will paste 8. In insert mode <C-r>=expression.
  Example:
    assign variable -> :let foo = expand('%')
    Paste in insert mode -> <C-r>=foo
    Paste in visual mode -> "=foo<cr>p (`"=` Enter evaluation register, `foo<cr>` yield foo value, `p` paste)

* `args` a list of manually added files
    - by default it is the dir/file where vim started
    - add all the md files in `cheatSheats` folder: `:args cheatSheats/*.md`
    - add a file by filename `:argadd {file_name}`, ex.: `:argadd {cheatSheats/unix.md}`
    - remove a file by filename `:argd {file_name}`, ex.: `:argd {cheatSheats/unix.md}`
* navigate in args `first`, `last`, `next`, `prev`

* record a macro
    1. `q{reg}`
    2. Actions
    3. `q` (stop the macro)
* execute a macro
    1. `@{reg}`
    2. `@@` execute last macro
    3. Select lines visually and then `:normal @{reg}`. This executes the
      macro in paralel, meaning if an error occur ot one of the lines it
      will not affect the others
* amend a macro
    1. `qa` records in reg a and `qA` appends new commands in reg `a`

* execute a macro for all args `:argdo normal @{reg}`
    - maybe you want to save all buffers after

* create a variable and amend it
    1. `:let i=0`
    2. `:let i+=1`
    - print value `:echo i`
    - paste the value
      - in insert mode: <C-r>=i<CR>
      - in normal mode: "=i<CR>p

* list all functions: `h function-list`

* search literally in buffer: `/\V`

* search by pattern without excaping `/\v`
    ex.: `/\v<(\w+)\_s+\1>` this regex finds duplicated words.
      - `<` beginning of a word
      - `>` end of a word
      - (\w+) match a word and save it under group 1
      - \_s+ match one or more spaces and new lines
      - \1 match group 1

* `q/` open search history

* `g/search_pattern/d` delete lines with matching pattern

* `g/search_pattern/#` Lists all matches of a search

* `%s/previous/next/gc` replaces string and asks for confirm

* `:cfdo` executes a command in all items of a quick fix window
     ex.: `:cfdo g/Practical/d | update`

* `:sort` can be used in visual mode

* `gn` and `gN` jump on next match and select it. Can be used with cmd ex.: `cgn`

* `ctags`
    `sudo apt-get install exuberant-ctags`
    `ctags --version` -> `Exuberant Ctags 5.8, Copyright (C) 1996-2009 Darren Hiebert`
    `:nnoremap <f5> :!ctags -R<CR>` -> run ctags from vim
    could have problems if trying to compile with node modules

* `effortless ctags with git` -> https://tbaggery.com/2011/08/08/effortless-ctags-with-git.html
* `ctags cmd` -> https://courses.cs.washington.edu/courses/cse451/10au/tutorials/tutorial_ctags.html
  :tselect, :tnext, :tprev, :tfirst, :tlast, :tag

* `:cnfile` `:cpfile` -> jumps to next file with matches

* `:cclose`/ `:copen` -> open/close the quickfix window

* Use quick fix list instead of window
  `:colder` and `:cnewer`

* Compiler in vim context means something that has document for input
    and list of errors for output `:h compiler`. Perfect of Rubocop and JSlint.

* Make in vim context runs compiler on a document and parses the errors, making
    them links in the doc. The errors are presented in a quickfix window. `:h make`

* `autocmd` listens for event to execute commands. ex.: `autocmd Filetype ruby`

* customizing generic auto completion: `:set complete-=i`

* enable `:h compl-omni` <C-x><C-o>

* vimcasts.org

* Fugitive
    Alternative to git add -p

    - Open Fugitive window: <leader>ks
    - Open file diff view:  `D`
    - Add specific line
      - Go to line on which you want to add
      - execute cmd:        `:diffput`
      - got to the other diff file and save it

* `g*` search for the word under the cursor without putting word breaks

* `zf` and `zo` toggles folding when fold method is manual

* `gq` in visual mode wraps long lines to 80 symbols

* `gf` takes you to the file beneath if 'path' is configured. Can be used with number ex.: 2gf

* `Ctrl-o` - back, opposite of `Ctrl-i`

* `]m` and `[m` - jump forward and back between method def in ruby
* `]M` and `[M` - jumps to method 'end' in ruby
* `]]` and `[[` - same but for classes and modules

* `:tags` - shows recent ctags jumps
* `Ctrl-t` - goes back one ctag file
* `g<Ctrl-t>` - opens all tags for this definition
* `:tselect` - opens the list of tags
* `gi` - goes to last insert mode
* `:<Ctrl-f>` same as `q:`

* `:Rak` - runs current file in tmux down

* `:lopen`/`:lclose` - opens/closes window containing errors and warnings
* `:lnext`/`:lprev` - to navigate through errors

* `:map ,t :cmd`/`:map <leader>e :cmd` - easy way to make a key binding runtime
  `:map ,t :sp \| e term://rspec %<cr>` -> example

Still don't get this search pattern `\.\ZS\W`

use https://github.com/tpope/rbenv-ctags to index ruby stdlib

plugins
  rails.vim
  visual star
  vim-abolish
  vim-syntastic/syntastic
  essential.vim

If Martin luther king wrote on VIM he would have a wish to:
  search only in a directory
  use quicklist
  network with nav tree scp
  how to duplicate a file
