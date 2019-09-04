### Appendix A - Cheat Sheet

#### Keyboard Shortcuts

**Global Shortcuts** (keys that work when TestComplete is running even if TestComplete does not have focus)

  |**Command**|**Default Key**|
  |---|---|
  |Pause script execution|SHIFT-10|
  |Fix Information|SHIFT-CTRL-A|
  |Record|SHIFT-F1|
  |Stop|SHIFT-F2|
  |Run|SHIFT-F3|
  |Pause recording|SHIFT-F11|
  |Low Level Record|SHIFT-F4|

**Key Mapping** (keys that work when TestComplete has focus, generally in the editors)

  |**Command/Section**|**Default**|**Visual Studio**|**Borland Classic**|
  |---|---|---|---|
  |**Debugging**|   |   |   |
  |Run                   |F9            |F5                  |F9|
  |Reset                 |CTRL-F2       |SHIFT-F5            |CTRL-F2|
  |Step Over             |F8            |F10                 |F8|
  |Trace Into            |F7            |F11                 |F7|
  |Run to Cursor         |F4            |F4                  |F4|
  |Switch Breakpoint     |F5            |F9                  |CTRL-F8|
  |View Evaluate           |CTRL-F7          |CTRL-F2             |CTRL-F4|
  |View Call Stack         |CTRL-ALT-S       |ALT-7               |CTRL-ALT-S|
  |View Watches            |CTRL-ALT-W       |ALT-3               |CTRL-ALT-W|
  |View Break Points       |CTRL-ALT-B       |CTRL-B              |CTRL-ALT-B|
  |**Project/Units**       |   |   |   |                                     
  |Close Page              |CTRL-F4          |CTRL-F4             |ALT-F3|
  |Save Unit               |CTRL-S           |CTRL-S              |CTRL-S|
  |Open Project            |CTRL-F11         |CTRL-SHIFT-0        |CTRL-F11|
  |New Project             |                |CTRL-SHIFT-N        |   |
  |Save All                                 |CTRL-SHIFT-S        |CTRL-SHIFT-S|
  |Display next page       |CTRL-TAB         |CTRL-TAB            |CTRL-TAB|
  |**Cursor movement**     |   |   |   |                                     
  |Cursor Left             |LEFT             |LEFT                |LEFT|
  |Cursor Right            |RIGHT            |RIGHT               |RIGHT|
  |Beginning of Line       |HOME             |HOME                |HOME|
  |End of Line             |END              |END                 |END|
  |Up one line             |UP               |UP                  |UP|
  |Down one line           |DOWN             |DOWN                |DOWN|
  |Up one page     | PGUP            | PGUP            | PGUP            |
  |Down one page   | PGDN            | PGDN            | PGDN            |
  |Beginning of Document    | CTRL-HOME       | CTRL-HOME       | CTRL-PGUP       |
  |End of Document | CTRL-END        | CTRL-END        | CTRL-PGDN       |
  |Move to word before    | CTRL-LEFT       | CTRL-LEFT       | CTRL-LEFT       |
  |Move to word after    | CTRL-RIGHT      | CTRL-RIGHT      | CTRL-RIGHT      |
  |**Delete operations**       |                 |                 |                 |
  |Delete character at cursor          | DEL             | DEL             | DEL             |
  |Delete character before cursor  | BACKSPACE       | BACKSPACE       | BACKSPACE       |
  |Delete current line  | CTRL-Y          | CTRL-SHIFT-L    | CTRL-Y          |
  |Delete previous word | CTRL-BACKSPACE  | CTRL-BACKSPACE  | CTRL-BACKSPACE  |
  |Delete next word     | CTRL-T          | CTRL-DEL        | CTRL-T          |
  |**Miscellaneous** |                 |                 |                 |
  |Indent selected block | CTRL-SHIFT-I **or** TAB    | CTRL-SHIFT-I    | CTRL-SHIFT-I    |
  |Unindent selected block | CTRL-SHIFT-U    | CTRL-SHIFT-U    | CTRL-SHIFT-U    |
  |Toggle insert/  | INS             | INS             | INS             |
  |overwrite mode  |                 |                 |                 |
  |Undo            | CTRL-Z **or** ALT- BACKSPACE  | CTRL-Z **or** ALT- BACKSPACE   | ALT-BACKSPACE   |
  |Redo            | SHIFT-CTRL-Z    | SHIFT-CTRL-Z    | ALT-SHIFT-BACKSPACE      |
  |Print           | CTRL-P          | CTRL-P          | CTRL-P          |
  |Scroll display up one line   | CTRL-UP         | CTRL-UP         | CTRL-W          |
  |Scroll display down one line  | CTRL-DOWN       | CTRL-DOWN       | CTRL-Z          |
  |Display context menu | ALT-F10   | ALT-F10   | ALT-F10   |
  |Find            | CTRL-F          | CTRL-F          | CTRL-F          |
  |Replace         | CTRL-R          | CTRL-H          | CTRL-R          |
  |Search Again    | F3              | F3              | CTRL-L          |
  |Select All      | CTRL-A          | CTRL-A          |                 |
  |Invoke Code Completion     | CTRL-SPACE      | CTRL-SPACE      | CTRL-SPACE      |
  |Code Templates  | CTRL-J          | CTRL-J          | CTRL-J          |
  | **Bookmarks**   |                 |                 |                 |
  |Set Numbered Bookmark    | CTRL-SHIFT-\#   | CTRL-SHIFT-\#   | CTRL-SHIFT-\#   |
  |Goto Numbered Bookmark   | CTRL-\#         | CTRL-\#         | CTRL-\#         |
  |Set Unnumbered Bookmark    |CTRL-SHIFT-\'  |        CTRL-SHIFT-\' |         CTRL-SHIFT-\'|
  |Goto Unnumbered Bookmark   |CTRL-\'         |       CTRL-\'  |              CTRL-\'|
  |**Clipboard**|   |   |   |                                                            
  |Cut to Clipboard           |CTRL-X or SHIFT- DEL   |CTRL-X or SHIFT- DEL   |CTRL-X or SHIFT- DEL|
  |Copy to Clipboard          |CTRL-C or CTRL-INS     |CTRL-C or CTRL-INS     |CTRL-C or CTRL-INS|
  |Paste from Clipboard       |CTRL-V or SHIFT-INS    |CTRL-V or SHIFT-INS    |CTRL-V or SHIFT-INS|

#### Keyboard Handling in Recorder

TestComplete will record all keys entered to the active control while recording except for any keys that are in the Global Shortcuts. 

**Global Shortcuts** (keys that work when TestComplete is running even if TestComplete does not have focus)

  |**Command**|**Default Key**|
  |---|---|
  |Pause script execution   |SHIFT-10|
  |Fix Information          |SHIFT-CTRL-A|
  |Record                   |SHIFT-F1|
  |Stop                     |SHIFT-F2|
  |Run                      |SHIFT-F3|
  |Pause recording          |SHIFT-F11|
  |Low Level Record         |SHIFT-F4|

#### Configuring Global Shortcuts

To access and change Global Shortcuts:

1.  Select **Tools \| Options** from the main menu.

2.  Select **General \| Global Shortcuts** from the Options dialog.

3.  Select the **Action**.

4.  Type in the new keyboard shortcut (note: if it is already in use, you will need to clear the one using it first).

![](../media/image366.png)

#### Configuring Keyboard Emulation

To access and change the keyboard emulation:

1.  Select **Tools \| Customize Keyboard\...** from the main menu.

2.  Choose the keyboard emulation that you want. (You can also set keyboard shortcuts for any command in this dialog).

![](../media/image367.png)