### Vim Use and Shortcuts

Vim Cheat Sheet: http://www.viemu.com/vi-vim-cheat-sheet.gif 

To open a new file in vim: `vim new_file.txt`

#### In Command Mode
To move the cursor:
* H --> Left
* J --> Down
* K --> Up
* L --> Right

To insert the cursor, and enter Edit Mode:
* i --> before cursor
* a --> after cursor

To select and work with lines of text:
* `Y` copies a line of text into the buffer
* `P` pastes it to the cursors current position
* `dd` deletes a whole line of text, and puts it into the buffer (i.e. cut)
* `yy` copies a whole line of text into the buffer

Working with files:
* `:w` to save
* `:wq` to save and quit
* `:q!` to quit and ignore changes

#### In Edit Mode
Press `esc` to get back into Command mode. 