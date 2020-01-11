= VIM COMMANDS
:source-highlighter: pygments
:pygments-style: manni
:sectnums:
:icons: font
:toc:
:toclevels: 6 


== Introduction
This document briefly explains the functionalities of different *vim* editor
commands. We assume that the reader has some experience working with vim
editor, and the aim here is to provide a cheat sheet for some important vim 
commands by logically organiging them.

== Vim Modes
Vim traces its ancestry back to *vi*, vi in turn traces its ancestry back to a
line editor called *ex*. The DNA of these early Unix text editors is preserved 
in modern vim. In accordance, vim preserves the modal architecture of these
ancestors, and exposes following modes.

=== Normal Mode
Normal mode is where you can run most of the vim commands. This is the default
mode in which Vim starts up.

=== Insert Mode
Insert mode is where you insert i.e. write the text.

=== Visual Mode
Visual mode is where you visually select a bunch of text so that you can run a
command/operation only on that part of the text.

=== Command-Line Mode
Command-Line mode is where you can run *ex* commands.


== Normal Mode Commands
=== Quit Vim
[%autowidth]
|===
|[red]#*ZZ*# | quit vim by saving changes if any
|===

=== Move Curser
==== Move Around Character
[%autowidth]
|===
|[red]#*l*# | move right of current character
|[red]#*h*# | move left of current character
|[red]#*k*# | move upward of current character
|[red]#*j*# | move downward of current character 
|===

==== Move Around Word
[%autowidth]
|===
|[red]#*w*#  | move to begin of word in forward direction
|[red]#*W*#  | move to begin of delimetted word in forward direction
|[red]#*b*#  | move to begin of word in backward direction
|[red]#*B*#  | move to begin of delimetted word in backward direction
|[red]#*e*#  | move to end of word in forward direction
|[red]#*E*#  | move to end of delimetted word in forward direction
|[red]#*ge*# | move to end of word in backward direction
|[red]#*gE*# | move to end of delimetted word in backward direction
|===

==== Move Around Line
[%autowidth]
|===
|[red]#*0*# | move to begin of current line
|[red]#*^*# | move to first non-blank character of current line
|[red]#*$*# | move to end of current line
|[red]#*-*# | move to first non-blank character of previous line
|[red]#*+*# | move to first non-blank character of next line
|===

==== Move Around Sentence
[%autowidth]
|===
|[red]#*)*#  | move to begin of sentence in forward direction
|[red]#*(*#  | move to begin of sentence in backward direction 
|===

==== Move Around Paragraph
[%autowidth]
|===
|[red]#*}*#  | move to begin of paragraph in forward direction
|[red]#*{*#  | move to begin of paragraph in backward direction
|===

==== Move Around Section 
[%autowidth]
|===
|[red]#*[[*# | move to begin of section in forward direction
|[red]#*]]*# | move to begin of section in backward direction
|===

==== Move Around Screen
[%autowidth]
|===
|[red]#*H*#       | move to head line of current screen
|[red]#*M*#       | move to mid line of current screen
|[red]#*L*#       | move to last line of current screen
|[red]#*C-f*#     | move forward one screen
|[red]#*C-b*#     | move backward one screen
|[red]#*C-d*#     | move forward one-half screen
|[red]#*C-u*#     | move backward one-half screen
|[red]#*z-ENTER*# | reposition current line to top of screen
|[red]#*z.*#      | reposition current line to mid of screen
|[red]#*z-*#      | reposition current line to bottom of screen
|===

==== Miscellaneous Moves
[%autowidth]
|===
|[red]#*gg*# | move to first line of file
|[red]#*G*#  | move to last line of file
|===


=== Search
==== Search Character
[%autowidth]
|===
|[red]#*fx*# | search forward, for character [red]#*x*# in current line
|[red]#*Fx*# | search backward, for character [red]#*x*# in current line
|[red]#*tx*# | search forward, for character before [red]#*x*# in current line
|[red]#*Tx*# | search backward, for character before [red]#*x*# in current line
|[red]#*;*#  | Repeat last [red]#*f*#, [red]#*F*#, [red]#*t*#, or [red]#*T*#
|[red]#*,*#  | Reverse search direction of last [red]#*f*#, [red]#*F*#, [red]#*t*#, or [red]#*T*#
|===

==== Search Word
[%autowidth]
|===
| [red]#***# | search forward, for current word
| [red]*#*   | search backward, for current word
|===

==== Search Pattern
[%autowidth]
|===
|[red]#*/pattern*# | search forward, for [red]#*pattern*#
|[red]#*?pattern*# | search backward, for [red]#*pattern*#
|[red]#*n*# repeat | forward, previous search
|[red]#*N*# repeat | backward, previous search
|===

==== Miscellaneous Searches
[%autowidth]
|===
|[red]#*%*# | search for the match of current parenthesis, brace, or bracket
|===


=== Mark
==== Mark Position 
[%autowidth]
|===
|[red]#*mx*# | place a mark [red]#*x*# at current curser postion
|===

==== Goto Marks
[%autowidth]
|===
|[red]#*`x*# | goto to mark [red]#*x*#
|[red]#*'x*# | goto to first non-blank character of line where mark [red]#*x*# is placed
|===

==== Goto Special Marks
[%autowidth]
|===
|[red]#*`.*# | goto to position where last change occurred in current buffer
|[red]#*`"*# | goto to position where last exited current buffer
|===


=== Edit
==== Replace
[%autowidth]
|===
|[red]#*r*# | replace current character (by a single character)
|[red]#*~*# | reverse case of current character (and move right)
|===

==== Delete
===== Delete Character
[%autowidth]
|===
|[red]#*x*#  | delete current character
|[red]#*X*#  | delete previous character 
|[red]#*dl*# | delete current character (same as [red]#*x*#)
|[red]#*dh*# | delete previous character (same as [red]#*X*#)
|===

===== Delete Around Word Boundary
[%autowidth]
|===
|[red]#*diw*# | delete current word
|[red]#*diW*# | delete current delimetted word
|[red]#*dw*#  | delete till begin of word in forward direction
|[red]#*dW*#  | delete till begin of delimetted word in forward direction
|[red]#*db*#  | delete till begin of word in backward direction
|[red]#*dB*#  | delete till begin of delimetted word in backward direction
|[red]#*de*#  | delete till end of word in forward direction
|[red]#*dE*#  | delete till end of delimetted word in forward direction
|[red]#*dge*# | delete till end of word in backward direction
|[red]#*dgE*# | delete till end of delimetted word in backward direction
|===

===== Delete Around Line Boundary
[%autowidth]
|===
|[red]#*d0*#  | delete till begin of current line
|[red]#*d^*#  | delete till first non-blank character of current line
|[red]#*d$*#  | delete till end of current line
|[red]#*D*#   | delete till end of current line (same as [red]#*d$*#)
|===

===== Delete Line(s)
[%autowidth]
|===
|[red]#*dd*# | delete current line
|[red]#*dk*# | delete line in upward direction 
|[red]#*d-*# | delete line in upward direction (same as [red]#*dk*#)
|[red]#*dj*# | delete line in downward diection
|[red]#*d+*# | delete line in downward diection (same as [red]#*dj*#)
|===

==== Yank (Copy)
===== Yank Character
[%autowidth]
|===
|[red]#*yl*# | copy current character
|[red]#*yh*# | copy previous character
|===

===== Yank Around Word Boundary
[%autowidth]
|===
|[red]#*yiw*# | copy current word
|[red]#*yiW*# | copy current delimetted word
|[red]#*yw*#  | copy till begin of word in forward direction
|[red]#*yW*#  | copy till begin of delimetted word in forward direction
|[red]#*yb*#  | copy till begin of word backward direction
|[red]#*yB*#  | copy till begin of delimetted word backward direction
|[red]#*ye*#  | copy till end of word in forward direction
|[red]#*yE*#  | copy till end of delimetted word in forward direction
|[red]#*yge*# | copy till end of word in backward direction
|[red]#*ygE*# | copy till end of delimetted word in backward direction
|===

===== Yank Around Line Boundary
[%autowidth]
|===
|[red]#*y0*# | copy till begin of current line
|[red]#*y^*# | copy till first non-blank character of current line
|[red]#*y$*# | copy till end of current line
|===

===== Yank Line(s)
[%autowidth]
|===
|[red]#*yy*# | copy current line
|[red]#*Y*#  | copy current line (same as [red]#*yy*#)
|[red]#*yk*# | copy line in upward direction 
|[red]#*y-*# | copy line in upward direction (same as [red]#*yk*#)
|[red]#*yj*# | copy line in downward direction
|[red]#*y+*# | copy line in downward direction (same as [red]#*yj*#)
|===


==== Put Deleted (or Yanked) Text
[%autowidth]
|===
|[red]#*p*# | put recently deleted (or yanked) text after current character
|[red]#*P*# | put recently deleted (or yanked) text before current character
|===

==== Miscellaneous Edits
[%autowidth]
|===
|[red]#*.*#   | repeat last edit command
|[red]#*u*#   | undo last edit
|[red]#*U*#   | restore recently edited line
|[red]#*C-r*# | redo last undo
|[red]#*J*#   | join current and immediate next line
|===


=== Switch To Insert Mode
==== Replace
[%autowidth]
|===
|[red]#*R*# | start replacing text from current character
|===

==== Insert
[%autowidth]
|===
|[red]#*i*# | start insertion before current curser
|[red]#*a*# | start insertion after current curser
|[red]#*I*# | start insertion before first non-blank character of current line
|[red]#*A*# | start insertion after last character of current line
|[red]#*o*# | start insertion in new line after current line
|[red]#*O*# | start insertion in new line before current line
|===

==== Change (Delete And Then Insert)
===== Change Character
[%autowidth]
|===
|[red]#*s*#  | delete current character, and start insertion
|[red]#*cl*# | delete current character, and start insertion (same as [red]#*s*#) 
|[red]#*ch*# | delete previous character, and start insertion
|===

===== Change Around Word
[%autowidth]
|===
|[red]#*ciw*# | delete current word, and start insertion
|[red]#*ciW*# | delete current delimetted word, and start insertion
|[red]#*cw*#  | delete till begin of word in forward direction, and start insertion
|[red]#*cW*#  | delete till begin of delimetted word in forward direction, and start insertion
|[red]#*cb*#  | delete till begin of word in backward direction, and start insertion
|[red]#*cB*#  | delete till begin of delimetted word in backward direction, and start insertion
|[red]#*ce*#  | delete till end of word in forward direction, and start insertion
|[red]#*cE*#  | delete till end of delimetted word in forward direction, and start insertion
|[red]#*cge*# | delete till end of word in backward direction, and start insertion
|[red]#*cgE*# | delete till end of delimetted word in backward direction, and start insertion
|===

===== Change Around Line
[%autowidth]
|===
|[red]#*c0*# | delete till begin of current line, and start insertion
|[red]#*c^*# | delete till first non-blank character of current line, and start insertion
|[red]#*c$*# | delete till end of current line, and start insertion
|[red]#*C*#  | delete till end of current line, and start insertion (same as [red]#*c$*#)
|===

===== Change Line(s)
[%autowidth]
|===
|[red]#*cc*# | delete current line, and start insertion
|[red]#*S*#  | delete current line, and start insertion (same as [red]#*cc*#)
|[red]#*ck*# | delete line in backward direction, and start insertion
|[red]#*c-*# | delete line in backward direction, and start insertion (same as [red]#*ck*#)
|[red]#*cj*# | delete line in forward direction, and start insertion
|[red]#*c+*# | delete line in forward direction, and start insertion (same as [red]#*cj*#)
|===


=== Switch To Visual Mode
[%autowidth]
|===
|[red]#*v*#   | switch to character-wise selection of visual mode
|[red]#*V*#   | switch to line-wise selection of visual mode
|[red]#*C-v*# | switch to block-wise selection of visual mode
|===

NOTE: Repetation of above commands more than once result in toggle between *visual* and *normal* mode


=== Switch To Command-Line Mode
[%autowidth]
|===
|[red]#*:*# | switch to command-line mode
|===


== Visual Mode Commands
=== Select
==== Character-wise Select
===== Select Character
[%autowidth]
|===
|[red]#*l*# | select in forward direction
|[red]#*h*# | select in backward direction
|[red]#*k*# | select in upward direction
|[red]#*j*# | select in downward direction
|===

===== Select Around Word
[%autowidth]
|===
|[red]#*iw*# | select current word
|[red]#*iW*# | select current delimetted word
|[red]#*w*#  | select till begin of word in forward direction
|[red]#*W*#  | select till begin of delimetted word in forward direction
|[red]#*b*#  | select till begin of word in backward direction
|[red]#*B*#  | select till begin of delimetted word in backward direction
|[red]#*e*#  | select till end of word in forward direction
|[red]#*E*#  | select till end of delimetted word in forward direction
|[red]#*ge*# | select till end of word in backward direction
|[red]#*gE*# | select till end of delimetted word in backward direction
|===

===== Select Around Line
[%autowidth]
|===
|[red]#*0*# | select till begin of current line
|[red]#*^*# | select till first non-blank character of current line
|[red]#*$*# | select till end of current line
|[red]#*-*# | select till begin of previous line
|[red]#*+*# | select till begin of next line
|===

==== Line-wise Select
[%autowidth]
|===
|[red]#*k*# | select in upward direction
|[red]#*j*# | select in downward direction
|===

==== Block-wise Select
[%autowidth]
|===
|[red]#*l*# | select in forward direction
|[red]#*h*# | select in backward direction
|[red]#*k*# | select in upward direction
|[red]#*j*# | select in downward direction
|===

==== Miscellaneous Selects
[%autowidth]
|===
|[red]#*gv*# | reselect last visual selection
|===


=== Move Around Selected Text
[%autowidth]
|===
|[red]#*o*# | toggle (curser moving) free-end of visually selected text
|===

=== Edit Selected Text
[%autowidth]
|===
|[red]#*d*# | delete selected text, and enter normal mode
|[red]#*c*# | delete selected text, and enter insert mode
|[red]#*y*# | yank (copy) selected text, and enter normal mode
|[red]#*u*# | convert characters in selected text to lower-case, and enter normal mode
|[red]#*U*# | convert characters in selected text to upper-case, and enter normal mode
|===

== Command-Line Mode Commands
=== Quit Vim
[%autowidth]
|===
|[red]#*:x*#  | quit vim, by saving changes if any (same as [red]#*ZZ*#)
|[red]#*:wq*# | quit vim, by saving changes if any (same as [red]#*ZZ*#)
|[red]#*:q*#  | quit vim (fails if changes were made)
|[red]#*:q!*# | quit vim (discarding edits)
|===

=== Save Changes
[%autowidth]
|===
|[red]#*:w*#  | save changes if any
|[red]#*:w!*# | save changes if any (overriding protection)
|[red]#*:w file*# | copy current file to [red]#*file*#, and swith to edit [red]#*file*#
|[red]#*:w! file*# | copy current file to [red]#*file*#, and swith to edit [red]#*file*# (overriding protection)
|===


