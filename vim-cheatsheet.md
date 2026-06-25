# Vim cheatsheet

Vim is a highly efficient text editor because almost every single key on your keyboard is mapped to an intentional action depending on what "mode" you are in.

By combining the absolute best structures, advanced combinations, and essential shortcuts from classic guides like `vim.rtorr.com`, Stanford's CS110 handout, and `devhints.io`, here is your ultimate, fully comprehensive Vim master cheat sheet.

***

### 1. Global Essentials & Modes

Vim runs in modes. To use any shortcut below, you must be in **Normal Mode** unless stated otherwise.

| Command               | Action Description                                                          |
| --------------------- | --------------------------------------------------------------------------- |
| `i`                   | **Insert mode:** Start typing text before the cursor position.              |
| `a`                   | **Append mode:** Start typing text right after the cursor position.         |
| `Esc` or `Ctrl + [`   | **Return to Normal Mode:** Escapes from any current mode or command string. |
| `:w`                  | **Save:** Write current changes to the file.                                |
| `:q`                  | **Quit:** Close the file (fails if there are unsaved changes).              |
| `:q!`                 | **Force Quit:** Exit immediately discarding all unsaved changes.            |
| `:wq` or `:x` or `ZZ` | **Save and Quit:** Save changes and close the editor in one quick motion.   |

***

### 2. Basic Navigation (The Home Row)

Avoid using the arrow keys so your hands never have to leave the typing home row.

| Command | Action Description                              |
| ------- | ----------------------------------------------- |
| `h`     | Move the cursor one character to the **left**.  |
| `j`     | Move the cursor down one line.                  |
| `k`     | Move the cursor up one line.                    |
| `l`     | Move the cursor one character to the **right**. |

***

### 3. Advanced Movement & Scrolling

| Command            | Action Description                                                              |
| ------------------ | ------------------------------------------------------------------------------- |
| `w`                | Jump forward to the start of the next **word**.                                 |
| `b`                | Jump backward to the start of the previous **word**.                            |
| `e`                | Jump forward to the **end** of the current or next word.                        |
| `ge`               | Jump backward to the **end** of the previous word.                              |
| `W` / `B` / `E`    | Same word movements as above, but treating punctuation as part of the word.     |
| `0`                | Jump directly to the absolute **beginning of the current line**.                |
| `^`                | Jump to the first **non-blank character** on the current line.                  |
| `$`                | Jump directly to the absolute **end of the current line**.                      |
| `gg`               | Jump straight to the **very first line** of the file.                           |
| `G`                | Jump straight to the **very last line** of the file.                            |
| `:#` (e.g., `:42`) | Jump directly to line number `#`.                                               |
| `Ctrl + d`         | Scroll down half a screen.                                                      |
| `Ctrl + u`         | Scroll up half a screen.                                                        |
| `Ctrl + f`         | Scroll down a full screen.                                                      |
| `Ctrl + b`         | Scroll up a full screen.                                                        |
| `%`                | Jump between matching pairs of parentheses `()`, brackets `[]`, or braces `{}`. |

***

### 4. Editing: Inserting, Deleting, and Changing

> **The Power of Operators:** In Vim, verbs like `d` (delete) and `c` (change) combine smoothly with nouns like `w` (word) or `$` (end of line). For instance, `dw` deletes a single word, and `d$` deletes everything to the end of the line.

| Command     | Action Description                                                              |
| ----------- | ------------------------------------------------------------------------------- |
| `I`         | Insert text at the absolute beginning of the line.                              |
| `A`         | Append text at the absolute end of the line.                                    |
| `o`         | Open a brand new line **below** the current one and enter Insert mode.          |
| `O`         | Open a brand new line **above** the current one and enter Insert mode.          |
| `x`         | Delete the single character directly under the cursor.                          |
| `X`         | Delete the single character directly before the cursor.                         |
| `dw`        | Delete from the cursor to the start of the next word.                           |
| `d$` or `D` | Delete everything from the cursor to the absolute end of the line.              |
| `dd`        | Delete the entire current line (also copies it to your clipboard/register).     |
| `cw`        | Change word: delete from cursor to end of word and enter Insert mode.           |
| `c$` or `C` | Change to end of line: clear text to the end and enter Insert mode.             |
| `cc`        | Change the entire line: clear it out entirely and enter Insert mode.            |
| `r`         | Replace just the single character under the cursor with the next key you press. |
| `R`         | Enter **Replace Mode**: overwrite text as you type until hitting Escape.        |
| `s`         | Substitute: delete the character under the cursor and enter Insert mode.        |
| `S`         | Substitute line: delete the entire line and enter Insert mode.                  |

***

### 5. Copy, Paste, Undo & Redo

| Command     | Action Description                                                     |
| ----------- | ---------------------------------------------------------------------- |
| `yy` or `Y` | **Yank (Copy)** the entire current line.                               |
| `yw`        | **Yank (Copy)** from the cursor to the end of the current word.        |
| `p`         | **Paste** copied text or deleted lines directly **after** the cursor.  |
| `P`         | **Paste** copied text or deleted lines directly **before** the cursor. |
| `u`         | **Undo** your last action.                                             |
| `Ctrl + r`  | **Redo** the last action you just undid.                               |
| `.`         | **Repeat** the exact last editing command you performed.               |

***

### 6. Search and Replace

| Command          | Action Description                                                                    |
| ---------------- | ------------------------------------------------------------------------------------- |
| `/pattern`       | Search forward through the file for your text `pattern`.                              |
| `?pattern`       | Search backward through the file for your text `pattern`.                             |
| `n`              | Repeat the previous search in the **same direction**.                                 |
| `N`              | Repeat the previous search in the **opposite direction**.                             |
| `*`              | Search forward for the exact word currently under your cursor.                        |
| `#`              | Search backward for the exact word currently under your cursor.                       |
| `:s/old/new`     | Replace the first occurrence of `old` with `new` on the current line.                 |
| `:s/old/new/g`   | Replace **every** occurrence of `old` with `new` on the current line.                 |
| `:%s/old/new/g`  | Replace **every** occurrence of `old` with `new` across the **entire file**.          |
| `:%s/old/new/gc` | Search and replace across the entire file, but **prompt for confirmation** each time. |

***

### 7. Visual Mode (Selecting Text)

| Command    | Action Description                                                               |
| ---------- | -------------------------------------------------------------------------------- |
| `v`        | Enter **Visual Mode**: select text character-by-character using navigation keys. |
| `V`        | Enter **Visual Line Mode**: select entire lines of text at a time.               |
| `Ctrl + v` | Enter **Visual Block Mode**: select text in vertical columns/rectangular blocks. |
| `o`        | Move the cursor to the opposite end of your active text selection.               |
| `d` or `x` | Delete the entire visually highlighted text selection.                           |
| `y`        | Yank (Copy) the entire visually highlighted text selection.                      |
| `>`        | Indent the selected text lines to the right.                                     |
| `<`        | Un-indent the selected text lines to the left.                                   |

***

### 8. Working with Multiple Files (Windows & Tabs)

#### Split Screen Windows

| Command                      | Action Description                                                        |
| ---------------------------- | ------------------------------------------------------------------------- |
| `:split filename` or `:sp`   | Open a file in a horizontal split screen window.                          |
| `:vsplit filename` or `:vsp` | Open a file in a vertical split screen window.                            |
| `Ctrl + w + navigation`      | Move your focus between open split windows (e.g., `Ctrl+w, h` goes left). |
| `Ctrl + w + =`               | Make all split windows equal in width and height.                         |
| `Ctrl + w + _`               | Maximize the height of the active split window.                           |
| \`Ctrl + w +                 | \`                                                                        |

#### Browser-like Tabs

| Command            | Action Description                               |
| ------------------ | ------------------------------------------------ |
| `:tabnew filename` | Open a new file in a brand new workspace tab.    |
| `:tabnext` or `gt` | Switch forward to the next tab to the right.     |
| `:tabprev` or `gT` | Switch backward to the previous tab to the left. |
| `:tabclose`        | Close the current workspace tab.                 |

***

### 9. Next-Level Efficiency: Multipliers & Text Objects

Vim lets you multiply almost any action by prefixing it with a number.

* **Format:** `[Number] + [Command]`
* `5w`  : Jump forward 5 words.
* `3dd` : Delete 3 entire lines at once.
* `42j` : Jump down exactly 42 lines.

#### Powerful Text Objects

* `diw` : **D**elete **I**nside **W**ord (deletes the word your cursor is on, even if you are in the middle of it).
* `ci"` : **C**hange **I**nside **"Quotes"** (wipes out everything inside the quotes and drops you into insert mode).
* `da)` : **D**elete **A**round )Parentheses (deletes the text inside the parentheses _and_ the parentheses symbols themselves).

***

### 10. Helpful Visual Customizations

Run these inside Vim by pressing `:` followed by the command to change your settings on the fly:

* `:set number` (or `:set nu`) : Show line numbers.
* `:set relativenumber` (or `:set rnu`) : Show relative line numbers (makes multiplying your movements incredibly easy).
* `:set syntax=on` : Turn on color-coded programming language syntax highlighting.
* `:set hlsearch` : Explicitly highlight all matches found during text search.
* `:noh` : Temporarily turn off search highlighting until your next search.
