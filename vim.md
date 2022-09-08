`i`brings **insert mode inside**

`a` brings **insert mode outside**

`I` gets to the **first non-white space character of the line**

`A` gets to the **end of the line** unlike `I` it goes to even end of any trailing white space.
`o` if you press `o` in normal mode of vim, it will get you to the insert mode in the new line with indentation of that respected language

`O`: guess what it does 

### File Navigation:

1. Open file navigation: `:Vex`

### Navigation in pop-up menu

1. `ctrl p` and `ctrl n`

### Window Split

1. `CTRL w + S` for horizontal split

2. `CTRL w + v` for vertical split

   `CTRL W` brings you into window mode

   #### Navigate between windows

   `CTRL w` the use normal navigation keys

### Marks, alternate files and jumps

Got to a particular line of a file and type `m <any letter>` then that line is marked with that letter. If the letter is upper-case then it'll be marked globally meaning you can return this line from any file, contrary if the letter is lower case then you can only get back here only from this file only. How to get to this mark? `'<the letter>` 

When you need to keep shift between two files, you can use `ctrl ^`; what it does is- loads the the previous opened file that you will see as pointed by `#` in registers (`:reg`).

To use jump lists, first type `:jumps`, what you see now is all the file history in order you opened. How do you visit through this history? (Always search in google and `h jumps` ). Here you go: `ctrl o`.



### source your vimrc/any file from command

`:so %` % refers to the current file; try these `:echo expand("%")`, `:%p`

### suggestion or tab-completion in command

`:h <tab>` you see all possible completion, to traverse that top down type ` ctrl n`  and `ctrl p` for opposite.

### Plugins

1. First you need a plugin manager; there are many, even vim has its own. But I've previously used: **[vim-plug](https://github.com/junegunn/vim-plug)**

   Now, we can install any plugin we want from github directly using this manager. 

2. Install **[fzf.vim](https://github.com/junegunn/fzf.vim)**, which is file finder. You will get user instruction there.

   some other that:

   ​      **[indentLine](https://github.com/Yggdroot/indentLine)** , **[ayu-vim](https://github.com/ayu-theme/ayu-vim)**(theme), **[ripgrep](https://github.com/BurntSushi/ripgrep)**(you can even use this file finder with fzf.vim, it's no vim specific stuff)     

### Searching over  and listing files

There are bunch of options that you can do. vim has its own searching option; read `:h grep`. There are lot to read about.  Also read `h quickfix`

Btw, let's see some practically.

```bash
:grep <pattern> file
# once you get all those mathches and press enter it's gone.
# how do you get them back
:copen # bring you the quickfix list
# traverse 
:cnext
:cprev
		
```

Search with ripgrep in vim

```bash
:Rg <pattern>
# a nice fzf.vim window will pop-up
# to traverse through this use up-down and select the find with <tab>
# that you want to bring to "Quick Fix", and click Enter
```

​	

