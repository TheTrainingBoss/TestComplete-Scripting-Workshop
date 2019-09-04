TestComplete© Scripting Workshop
by Alain "Lino" Tadros
------------------------------------------------------------

#### Welcome to TestComplete Scripting Workshop


##### © 2019 Alain "Lino "Tadros

All rights reserved. No parts of this work may be reproduced in any form or by any means - graphic, electronic, or mechanical, including photocopying, recording, taping, or information storage and retrieval  systems - without the written permission of the publisher.

Products that are referred to in this document may be either trademarks and/or registered trademarks of the respective owners. The publisher and the author make no claim to these trademarks.

While every precaution has been taken in the preparation of this document, the publisher and the author assume no responsibility for errors or omissions, or for damages resulting from the use of information contained in this document or from the use of programs and source code that may accompany it. In no event shall the publisher and the author be liable for any loss of profit or any other commercial damage caused or alleged to have been caused directly or indirectly by this document.

![](./media/testcomplete_github.png)

**Table of Contents**

[Overview of TestComplete](./Overview/readme.md)
--------------------------------------------------------

[Scripting](./Scripting/readme.md)
--------------------------

[Project Organization](./Project%20Organization/readme.md)
------------------------------------------------

[Test Log](./Test%20Log/readme.md)
------------------------

[Stores and Checkpoints](./Stores%20and%20Checkpoints/readme.md)
----------------------------------------------------

[Name Mapping](./Name%20Mapping/readme.md)
---------------------------------

[TestComplete Debugging](./Debugging/readme.md)
-----------------------------------------------------

[Event Handling](./Event%20Handling/readme.md)
-------------------------------------

[Data Driven Testing](./Data%20Driven%20Testing/readme.md)
-----------------------------------------------

[Web Testing](./Web%20Testing/readme.md)
-------------------------------

[Mobile](./Mobile/readme.md)
---------------------

[Web Services Testing](./Web%20Services%20Testing/readme.md)
-------------------------------------------------

[Distributed Testing](./Distributed%20Testing/readme.md)
----------------------------------------

[Manual Testing](./Manual%20Testing/readme.md)
----------------------------------------

[Low Level Procedures](./Low%20Level%20Procedures/readme.md)
-----------------------------------------------

[User Forms](./User%20Forms/readme.md)
----------------------------------------

[Best Practices](./Best%20Practices/readme.md)
-------------------------------------

[Appendix A - Cheat Sheet](./Cheat%20Sheet/readme.md)
------------------------------------------------

[Appendix B - Types of Testing](./Types%20of%20Testing/readme.md)
-------------------------------------------------------------------















### Appendix A - Shortcuts

[]{#SmartBear .anchor}

19. **Appendix A - Cheat Sheet**

> **Keyboard Shortcuts**
>
> **Global Shortcuts** (keys that work when TestComplete is running even
> if TestComplete does not have focus)

  **Command**              **Default Key**
  ------------------------ -----------------
  Pause script execution   SHIFT-10
  Fix Information          SHIFT-CTRL-A
  Record                   SHIFT-F1
  Stop                     SHIFT-F2
  Run                      SHIFT-F3
  Pause recording          SHIFT-F11
  Low Level Record         SHIFT-F4

> **Key Mapping** (keys that work when TestComplete has focus, generally
> in the editors)

  **Command/Section**   **Default**   **Visual Studio**   **Borland Classic**
  --------------------- ------------- ------------------- ---------------------
  **Debugging**                                           
  Run                   F9            F5                  F9
  Reset                 CTRL-F2       SHIFT-F5            CTRL-F2
  Step Over             F8            F10                 F8
  Trace Into            F7            F11                 F7
  Run to Cursor         F4            F4                  F4
  Switch Breakpoint     F5            F9                  CTRL-F8

  **Command/Section**     **Default**      **Visual Studio**   **Borland Classic**
  ----------------------- ---------------- ------------------- ---------------------
  View Evaluate           CTRL-F7          CTRL-F2             CTRL-F4
  View Call Stack         CTRL-ALT-S       ALT-7               CTRL-ALT-S
  View Watches            CTRL-ALT-W       ALT-3               CTRL-ALT-W
  View Break Points       CTRL-ALT-B       CTRL-B              CTRL-ALT-B
  **Project/Units**                                            
  Close Page              CTRL-F4          CTRL-F4             ALT-F3
  Save Unit               CTRL-S           CTRL-S              CTRL-S
  Open Project            CTRL-F11         CTRL-SHIFT-0        CTRL-F11
  New Project                              CTRL-SHIFT-N        
  Save All                                 CTRL-SHIFT-S        CTRL-SHIFT-S
  Display previous page   CTRL-SHIFT-TAB   CTRL-SHIFT-TAB      CTRL-SHIFT-TAB
  Display next page       CTRL-TAB         CTRL-TAB            CTRL-TAB
  **Cursor movement**                                          
  Cursor Left             LEFT             LEFT                LEFT
  Cursor Right            RIGHT            RIGHT               RIGHT
  Beginning of Line       HOME             HOME                HOME
  End of Line             END              END                 END
  Up one line             UP               UP                  UP
  Down one line           DOWN             DOWN                DOWN

+-----------------+-----------------+-----------------+-----------------+
| **Command/Secti | **Default**     | **Visual        | **Borland       |
| on**            |                 | Studio**        | Classic**       |
+=================+=================+=================+=================+
| Up one page     | PGUP            | PGUP            | PGUP            |
+-----------------+-----------------+-----------------+-----------------+
| Down one page   | PGDN            | PGDN            | PGDN            |
+-----------------+-----------------+-----------------+-----------------+
| Beginning of    | CTRL-HOME       | CTRL-HOME       | CTRL-PGUP       |
| Document        |                 |                 |                 |
+-----------------+-----------------+-----------------+-----------------+
| End of Document | CTRL-END        | CTRL-END        | CTRL-PGDN       |
+-----------------+-----------------+-----------------+-----------------+
| Move to word    | CTRL-LEFT       | CTRL-LEFT       | CTRL-LEFT       |
| before          |                 |                 |                 |
+-----------------+-----------------+-----------------+-----------------+
| Move to word    | CTRL-RIGHT      | CTRL-RIGHT      | CTRL-RIGHT      |
| after           |                 |                 |                 |
+-----------------+-----------------+-----------------+-----------------+
| **Delete        |                 |                 |                 |
| operations**    |                 |                 |                 |
+-----------------+-----------------+-----------------+-----------------+
| Delete          | DEL             | DEL             | DEL             |
| character at    |                 |                 |                 |
| cursor          |                 |                 |                 |
+-----------------+-----------------+-----------------+-----------------+
| Delete          | BACKSPACE       | BACKSPACE       | BACKSPACE       |
| character       |                 |                 |                 |
| before cursor   |                 |                 |                 |
+-----------------+-----------------+-----------------+-----------------+
| Delete current  | CTRL-Y          | CTRL-SHIFT-L    | CTRL-Y          |
| line            |                 |                 |                 |
+-----------------+-----------------+-----------------+-----------------+
| Delete previous | CTRL-BACKSPACE  | CTRL-BACKSPACE  | CTRL-BACKSPACE  |
| word            |                 |                 |                 |
+-----------------+-----------------+-----------------+-----------------+
| Delete next     | CTRL-T          | CTRL-DEL        | CTRL-T          |
| word            |                 |                 |                 |
+-----------------+-----------------+-----------------+-----------------+
| **Miscellaneous |                 |                 |                 |
| **              |                 |                 |                 |
+-----------------+-----------------+-----------------+-----------------+
| Indent selected | CTRL-SHIFT-I    | CTRL-SHIFT-I    | CTRL-SHIFT-I    |
| block           | **or** TAB      |                 |                 |
+-----------------+-----------------+-----------------+-----------------+
| Unindent        | CTRL-SHIFT-U    | CTRL-SHIFT-U    | CTRL-SHIFT-U    |
| selected block  | **or**          |                 |                 |
|                 |                 |                 |                 |
|                 | SHIFT-TAB       |                 |                 |
+-----------------+-----------------+-----------------+-----------------+
| Toggle insert/  | INS             | INS             | INS             |
| overwrite mode  |                 |                 |                 |
+-----------------+-----------------+-----------------+-----------------+

+-----------------+-----------------+-----------------+-----------------+
| **Command/Secti | **Default**     | **Visual        | **Borland       |
| on**            |                 | Studio**        | Classic**       |
+=================+=================+=================+=================+
| Undo            | CTRL-Z **or**   | CTRL-Z **or**   | ALT-BACKSPACE   |
|                 | ALT- BACKSPACE  | ALT- BACKSPACE  |                 |
+-----------------+-----------------+-----------------+-----------------+
| Redo            | SHIFT-CTRL-Z    | SHIFT-CTRL-Z    | ALT-SHIFT-      |
|                 | **or**          | **or**          | BACKSPACE       |
|                 |                 |                 |                 |
|                 | ALT-SHIFT-      | ALT-SHIFT-      |                 |
|                 | BACKSPACE       | BACKSPACE       |                 |
+-----------------+-----------------+-----------------+-----------------+
| Print           | CTRL-P          | CTRL-P          | CTRL-P          |
+-----------------+-----------------+-----------------+-----------------+
| Scroll display  | CTRL-UP         | CTRL-UP         | CTRL-W          |
| up one line     |                 |                 |                 |
+-----------------+-----------------+-----------------+-----------------+
| Scroll display  | CTRL-DOWN       | CTRL-DOWN       | CTRL-Z          |
| down one line   |                 |                 |                 |
+-----------------+-----------------+-----------------+-----------------+
| Display context | ALT-F10 (Code   | ALT-F10 (Code   | ALT-F10 (Code   |
| menu            |                 |                 |                 |
|                 | Editor only)    | Editor only)    | Editor only)    |
+-----------------+-----------------+-----------------+-----------------+
| Find            | CTRL-F          | CTRL-F          | CTRL-F          |
+-----------------+-----------------+-----------------+-----------------+
| Replace         | CTRL-R          | CTRL-H          | CTRL-R          |
+-----------------+-----------------+-----------------+-----------------+
| Search Again    | F3              | F3              | CTRL-L          |
+-----------------+-----------------+-----------------+-----------------+
| Select All      | CTRL-A          | CTRL-A          |                 |
+-----------------+-----------------+-----------------+-----------------+
| Invoke Code     | CTRL-SPACE      | CTRL-SPACE      | CTRL-SPACE      |
| Completion      |                 |                 |                 |
+-----------------+-----------------+-----------------+-----------------+
| Code Templates  | CTRL-J          | CTRL-J          | CTRL-J          |
+-----------------+-----------------+-----------------+-----------------+
| **Bookmarks**   |                 |                 |                 |
+-----------------+-----------------+-----------------+-----------------+
| Set Numbered    | CTRL-SHIFT-\#   | CTRL-SHIFT-\#   | CTRL-SHIFT-\#   |
| Bookmark        |                 |                 |                 |
+-----------------+-----------------+-----------------+-----------------+
| Goto Numbered   | CTRL-\#         | CTRL-\#         | CTRL-\#         |
| Bookmark        |                 |                 |                 |
+-----------------+-----------------+-----------------+-----------------+

  **Command/Section**        **Default**            **Visual Studio**      **Borland Classic**
  -------------------------- ---------------------- ---------------------- ----------------------
  Set Unnumbered Bookmark    CTRL-SHIFT-\'          CTRL-SHIFT-\'          CTRL-SHIFT-\'
  Goto Unnumbered Bookmark   CTRL-\'                CTRL-\'                CTRL-\'
  **Clipboard**                                                            
  Cut to Clipboard           CTRL-X or SHIFT- DEL   CTRL-X or SHIFT- DEL   CTRL-X or SHIFT- DEL
  Copy to Clipboard          CTRL-C or CTRL-INS     CTRL-C or CTRL-INS     CTRL-C or CTRL-INS
  Paste from Clipboard       CTRL-V or SHIFT-INS    CTRL-V or SHIFT-INS    CTRL-V or SHIFT-INS

> []{#Keyboard_Handling_in_Recorder .anchor}**Keyboard Handling in
> Recorder**
>
> TestComplete will record all keys entered to the active control while
> recording except for any keys that are in the Global Shortcuts.
>
> **Global Shortcuts** (keys that work when TestComplete is running even
> if TestComplete does not have focus)

  **Command**              **Default Key**
  ------------------------ -----------------
  Pause script execution   SHIFT-10
  Fix Information          SHIFT-CTRL-A
  Record                   SHIFT-F1
  Stop                     SHIFT-F2
  Run                      SHIFT-F3
  Pause recording          SHIFT-F11
  Low Level Record         SHIFT-F4

> []{#Configuring_Global_Shortcuts .anchor}**Configuring Global
> Shortcuts**
>
> To access and change Global Shortcuts:

78. Select **Tools \| Options** from the main menu.

79. Select **General \| Global Shortcuts** from the Options dialog.

80. Select the **Action**.

81. Type in the new keyboard shortcut (note: if it is already in use,
    you will need to clear the one using it first).

![](./media/image328.png){width="5.960137795275591in"
height="3.126457786526684in"}

> **Figure 237 \--Global Shortcuts**
>
> []{#Configuring_Keyboard_Emulation .anchor}**Configuring Keyboard
> Emulation**
>
> To access and change the keyboard emulation:

1.  Select **Tools \| Customize Keyboard\...** from the main menu.

2.  Choose the keyboard emulation that you want. (You can also set
    keyboard shortcuts for any command in this dialog).

![](./media/image329.png){width="4.519971566054243in"
height="4.927083333333333in"}

> **Figure 238 \-- Customize Keyboard Dialog**

### Appendix B - Types of Testing

20. []{#Appendix_B_-_Types_of_Testing .anchor}**Appendix B - Types of
    Testing**

> []{#Types_of_Testing .anchor}**Types of Testing**

#### Manual Testing

> Manual Testing is where a tester methodically exercises the features
> of a product or product area without the aid of test automation. The
> single greatest strength of manual testing is that it is truly
> real-world testing, meaning that the tester can utilize the
> application under test the same way an end user would. Through manual
> testing the tester can provide a wide variety of feedback about the
> application under test not limited to simply reproducing bugs.
>
> Manual tests are difficult to perform on a regular basis. The major
> weakness of manual testing is that it is time consuming, tedious and
> requires extended periods of focused attention. Manual testing tends
> to be quite error prone, leading to situations where consistently
> reproducing a bug can be very difficult.

#### Functional Testing

> Functional Testing focuses on interactions with an application\'s user
> interface (UI) via the mouse, keyboard or other input device with
> particular attention to how the application visually responds to
> input. The goal of Functional Testing is to methodically cover all of
> the various UI features exposed by an application. Functional Testing
> should be highly organized and structured in a manner that allows for
> additional tests to easily be incorporated as new features are added.

#### Unit Testing

> Unit Testing focuses on smaller atomic portions of an application.
> Typically, Unit Testing requires internal knowledge of how an
> application performs and seeks to test portions (objects, methods and
> function) of an application in isolation. In many cases, applications
> have to be designed with Unit Testing in mind in order for this type
> of testing to be truly effective. The benefit of unit testing is that
> it tends to force application developers to write smaller, well
> defined routines with fewer dependencies allowing for highly specific
> tests to be developed.

#### Regression Testing

> Regression Testing is the process of executing tests in a repeatable
> manner and comparing the latest results with previous test executions
> to ensure that the same outcome is achieved. Regression Testing is
> extremely important and is the means of realizing the value of test
> automation. Repeatedly executing tests over time allows you to verify
> the application is still performing as intended.

#### Distributed Testing

> Distributed Testing is the act of farming different portions of a test
> out to separate machines for execution. Distributed Testing is useful
> for simulating real world interactions on a networked application such
> as a web site or web service and can exercise functionality designed
> to handle concurrent use of application resources including, but not
> restricted to data.

#### HTTP Performance Testing

> HTTP Performance Testing is the simulation of real-world interactions
> with a web application from multiple machines. TestComplete provides
> the ability to leverage networked computers and virtual users to
> simultaneously submit HTTP transactions to a web application.

#### Multi-Tier

> In software development there are typically three Tiers which are used
> to describe various aspects of an application they are Client Tier,
> Middle Tier and Data Tier. These are each defined as:
>
> **Client** \-- The user interface or presentation of an application
> and its data which is typically covered through Functional Testing.
>
> **Data Tier** \-- The storage of an application\'s data which can be
> exercised by Functional Testing as well as Unit Testing
>
> **Middle Tier** \-- Refers to the portion of the application
> responsible for moving data back and forth between the Client and the
> Data Tiers. The code that resides in this Tier can be tested from
> either the Client Tier via Functional testing or through Unit Testing
> on the code in the Middle Tier itself. Keep in mind that these are not
> strict rules as to which type of testing should be used but more
> illustrative how the different types of testing can be used.
>