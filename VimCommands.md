# VIM tips I keep forgtting
Please [mail me](mailto:christian@twobulls.com) for comments or to add more tips.

This file is also hosted on [GitHub](https://github.com/cschladetsch/docs/blob/master/NewVimCommands.md).

I know/knew all these, but keep forgetting to use them, so I started maintaining this file. 

**Note** *that not all Vims, especially plugins to IDEs, provide all Vim commands.*

## Delete all lines that match a pattern

See [here](http://vim.wikia.com/wiki/Delete_all_lines_containing_a_pattern) for details, but the basics are:

	:g/pattern/d
	
To delete all blank lines:

	:g/^$/d
	:g/^\s*$/d	# all lines that are just whitespace

## Don't Leave Insert Mode as Much
You may well jump between normal and insert modes a lot. Here's some tips to avoid the context swaps:

### Executing commands
* When inserting text, press **`^O`** then any normal-mode vim command. After that command completes, you will be returned to insert mode.
	* So to go up 4 lines, type **`^Ok`** and you will be back in insert mode.

### Inserting yanked text
* To insert the current contents of the copy buffer while in insert mode, press **`^R"`**
* To insert contents of a register, say register 'a' while in insert mode, press **`^Ra`**

## Showing previous copy buffers

	:registers
	
Shows all previous yanked text with associated register numbers.

## Word searching under cursor

* **`*`** search word under cursor forward
* **`#`** search word under cursor backward.
* Both work with **`n`** to seach next, **`N`** to search back (with direction changed for **`*`** and **`#`**

## Changing case

* Toggle case "HellO" to "hELLo" with **`g~`** then a movement.
* Uppercase "HellO" to "HELLO" with **`gU`** then a movement.
* Lowercase "HellO" to "hello" with **`gu`** then a movement.
* Lowercase entire Line: **`Vgu`**

## Undo/Redo

* **`INu`**	Undo N times
* **`N^R`**	Redo N times

## Insert a Word/Letter in front of every line
* Move to the start of the first line in your range (**`gg`** for first line, **`^`** to move to the start)
* **`<C-V>`**
* Move down to the last line in your range
* **`Ifoo<ESC>`**

That would insert foo at the start of each line.

## Replacing word with what is in register

* **yiw**   
	*  Yank inner word (copy word under cursor, say "first").
	* Move the cursor to another word (say "second").
* **viwp**
	* Select "second", then replace it with "first".

# Bundles
First of all, I use Vundle as my bundle manager. There are a few others around as well, but Vundle works for me.

Here are the bundles I use:

* YouCompleteMe/
* auto-pairs/
* nerdcommenter/
* nerdtree/
* omnisharp-vim/
* rainbow_parentheses.vim/
* syntastic/
* tagbar/
* tlib_vim/
* vim-addon-mw-utils/
* vim-airline/
* vim-colors-solarized/
* vim-colorschemes/
* vim-csharp/
* vim-dispatch/
* vim-easymotion/
* vim-fugitive/
* vim-gitgutter/
* vim-multiple-cursors/
* vim-snipmate/
* vim-snippets/

Of these, **YouCompleteMe** (YCM) and **NERDTree** are the most useful. **Tagbar** gives things like Git info in your status bar etc.

**Syntastic** gives syntax highlighting to pretty much eveything like bash scripts, vim scripts, .gitignore, etc etc.

However, **YCM** has a compiled component and attention must be given when setting it up. But when it is, you get C# and C++ and even Python *Goto Definition* and automatic *Intellisense*.
