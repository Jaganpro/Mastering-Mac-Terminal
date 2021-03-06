# Vim
This repo introduces basics of Vim and its usage.

### Check Vim Installation and Version

Most of the Mac computers should have VIM pre-installed

![image](https://user-images.githubusercontent.com/2145211/48574771-06d7f480-e8de-11e8-8294-f3fda37adeea.png)

If VIM is not installed, please use homebrew to install it

```
brew install vim
```

### Introduction

Vim is a Free and Open Source(FOSS) advanced text editor. It is highly configurable.
It different from other editors because it introduces the concept of Modality (Ie, it has different modes).
We spend more time reading code than writing it. VIM is optimized for what you do most (Ie, Reading/Navigating Text)

There are 3 different types of modes in VIM:

* `Insert Mode` -- In this mode we are able to write text in the Editor
* `Normal Mode [or] Command Mode` -- In this mode we are able to navigate inside the Editor
* `Visual Mode` -- Mainly used to Select Text. There are variations in the text.  

### Navigating between modes

* To go from `Normal Mode` to `Insert Mode`, press `i`
* To go from `Normal Mode` to `Visual Mode`, press `v`
* To go from `Insert Mode` to `Normal Mode`, press `Esc`
* To go from `Visual Mode` to `Normal Mode`, press `Esc`

### Opening VIM Editor

Just type `vim` to get into VIM editor

```
vim
```

[OR] if you want to open a file directly in VIM editor

```
vim vimtutordemo.txt
```

### Opening files in VIM Editor

If VIM editor is already open, we can open a file by issuing the following command [Opens in NORMAL Mode]

```
:o vimtutordemo.txt
```

If VIM editor is already open, we can edit the file by issuing the following command [Opens in EDIT Mode].

```
:e vimtutordemo.txt
```

NOTE: Here `:e` short form for EDIT. `:o` is the short form for OPEN.

![image](https://user-images.githubusercontent.com/2145211/48583941-7a85fb80-e8f6-11e8-8be9-348b5d7b0de8.png)


### Closing the VIM Editor (Quit)

The below command will attempt to quit the editor. It will fail if there are any unsaved changes.
```
:q
```

This will close the editor without saving the file.
```
:q! 
```

### Saving a file in VIM Editor

```
:saveas <filename>
```

write(save) the file, but don't exit.
```
:w <filename>
```

If you want to quit vim and save the file, use the following command 
```
:wq
```

### Moving around in VIM Editor (Cursor Movements) [Available in NORMAL MODE] 

* (hjkl combo) (Basic Arrow keys replacements)
  * `h` - move cursor left
  * `j` - move cursor down
  * `k` - move cursor up
  * `l` - move cursor right

* (wWeEbB Combo) (Tip to Remember -- WEB) (Jumping between words)
  * `w` - Jump forward to the start of the word
  * `W` - Jump forward to the start of the word (Words can contain puntuation)
  * `e` - Jump forward to the end of the word
  * `E` - Jump forward to the end of the word (Words can contain puntuation)
  * `b` - Jump backwards to the start of the word
  * `B` - Jump forward to the end of the word (Words can contain puntuation)
  
* (0$) (Line Navigation)
  * `0` - Jump to the start of the line
  * `$` - Jump to the end of the line
  
* (){} (Sentence and Paragraph Navigation)
  * `}` - Jump to next Paragraph ( or function/block when editing code)
  * `{` - Jump to previous Paragraph
  * `)` - Jump to next Sentence
  * `(` - Jump to Previous Sentence

* (HML Combo) (Tip to Remember - High, Medium, Low) (Jumping within current Screen)
  * `H` - move to the top of the screen
  * `M` - move to the middle of the screen
  * `L` - move to the bottom of the screen
  
* (ctrl-b,f,d,u) (Screen Navigation)
  * `ctrl+f` - Move Forward a Page
  * `ctrl+b` - Move Backward a Page
  * `ctrl+d` - Move forward 1/2 screen
  * `ctrl+u` - Move back 1/2 screen

* (ggG) (Document Navigation)
  * `gg` - Jump to first line of the document
  * `G` - Jump to last line of the document

### Advanced movements around VIM [Available in NORMAL MODE] 

Get familier with usage of Arguments in VIM. For example,
If we want to skip and go down 10 lines, we can use the following: (Ie, it is executing 'j' command 10 times)

```
10j
```

Backus Normal Form style movement commands are supported in VIM.
In short:

* `fx` - Jump to next occurance of character x
* `tx` - Jump to before next occurance of character x

SYNTAX:
```
[(n)um] <verb> <n(o)un>

Anything in [] --> Optional
Anything in <> --> Required
```

* `[n]f<o>` - Forward until the (nth) (o) (Inclusive)
* `[n]F<o>` - Backward until the (nth) (o) (Inclusive)
* `[n]t<o>` - Forward until the (nth) (o) (Exclusive)
* `[n]T<o>` - Backward until the (nth) (o) (Exclusive)


### Inserting/Appending Text (Sounds live vowels to me!) [Available in INSERT MODE] 

* `i` - Insert before the cursor
* `I` - Insert at the beginning of the line
* `a` - Insert (Append) after the cursor
* `A` - Insert (Append) at the end of the line
* `o` - Append (Open) a new line below the current line
* `O` - Append (Open) a new line above the current line
* `ea` - Insert (Append) at the end of the word

### Editing Text [Available in INSERT MODE] 

* `r` - replace a single character
* `cc` - change (replace) entire line
* `cw` - change (replace) to the end of word
* `c$` - change (replace) to the end of the line
* `s` - delete character and (substitute) text
* `S` - delete line and (substitute) text (Same as `cc`)

* `u` - Undo
* `Ctrl + r` - Redo
* `.` - Repeat last command

### Marking / Highlighting Text [Available in VISUAL MODE] 

Visual mode is usually used to highlight any given text in the editor

* `v` - to get into visual mode.
* `Shift + v` - to highlight entire line during selection
* `y` - Yank (Copy) Marked Text
* `d` - Delete Marked Text
* `aw` - mark a word
* `ab` - a block with ()
* `aB` - a block with {}
* `ib` - inner block with ()
* `iB` - inner block with {}

### Cut and Paste in VIM [Available in VISUAL MODE]

COPY
* `yy` - yank(copy) a line
* `2yy` - yank(copy) 2 lines
* `yw` - yank(copy) the characters of the word from the cursor position to the starting of next work
* `y$` - yank(copy) to the end of the line

PASTE
* `p` - put(paste) the clipboard after cursor
* `P` - put(paste) before cursor

DELETE
* `dd` - delete(cut) a line
* `2dd` - delete(cut) 2 lines
* `dw` - delete(cut) the characters of the word from the cursor position to the start of the word
* `D` - delete
* `d$` - delete(cut) to the end of the line
* `x` - delete(cut) character

### Search and Replace (Within a single file)

SEARCH
* `/<searchstring>` - search for pattern
* `?<searchstring>` - search backward for pattern

NAVIGATION on HIGHLIGHTED SEARCH
* `n` - repeat search in same direction (Next)
* `N` - repeat search in opposite direction (Next)

REPLACE
* `:%s/old/new/g` - replace all `old text` with `new text` throught the file (g - Global)
* `:%s/old/new/gc` - replace all `old text` with `new text` throught the file with confirmation (gc - Global with Confirmation)

### Search in Multiple Files

Coming Soon!

### Tab Management in VIM

Coming Soon!

### VIM Cheatsheet
	
![image](https://user-images.githubusercontent.com/2145211/48723633-22504180-ebf5-11e8-8aad-c9a7ebf61846.png)

Credits for VIM Cheatsheet: www.viemu.com
