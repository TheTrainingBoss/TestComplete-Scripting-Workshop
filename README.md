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









### Low Level Procedures

Low Level Procedures
====================

Objectives
----------

> This chapter explains TestComplete Low Level Procedure functionality
> and how it can be leveraged to deal with situations where they may be
> no easy alternative. You'll learn how to record, edit and execute Low
> Level Procedures. Along the way you will learn how Low-Level
> Procedures differ from standard test recordings, when to use a
> Low-Level Procedure and the difference between Window and Screen Low
> Level Procedures.

About Low Level Procedures
--------------------------

> Low Level Procedures are an alternative recording type provided by
> TestComplete where actual mouse and keyboard events are recorded. Low
> Level Procedures differ dramatically from standard recordings where
> TestComplete records higher level actions against specific onscreen
> objects.

#### Low Level Procedure Types

> There are two kinds of Low Level Procedures:
>
> **Screen Coordinates** \-- Captures events relative to the entire
> screen where the top left-hand corner of the screen is 0,0.
>
> **Window Coordinates** \-- Captures events relative to a user selected
> Window where the top left-hand corner of the window is 0,0.
>
> Window Coordinate Low Level Procedures tend to be more reliable as
> they are unaffected by the location of the selected window and will
> playback relative to the Window\'s current screen location.

#### When To Use Low Level Procedures

> From the outset, tests that rely on screen coordinates generally are a
> bad idea and usually that holds true regardless of which tool you're
> using. However, in certain situations you may find yourself attempting
> to record a scenario that simply refuses to playback properly due to
> the complexity of capturing a user\'s intent via a recorder. In these
> cases, resorting to Low Level Procedures can, at the very least, serve
> as a stop-gap until alternative solutions can be developed.
>
> Additionally, you can work on applications using third party controls
> not directly supported by TestComplete and that provide no visibility
> into the client region of the control such as a custom grid.

Recording Low Level Procedures
------------------------------

> In the \"Web Testing\" chapter we looked at a Web application that
> used JavaScript to dynamically display menu items on screen. The
> application poses an interesting challenge for GUI recorders that tend
> to capture interactions with controls such as clicks and keystrokes.
> Let\'s take a look at recording a Low-Level Window Coordinates
> Procedure to handle the menu selection and understand this alternative
> approach to recording.

#### Low Level Window Coordinates Procedure

67. For starters we\'ll launch Internet Explorer and browse to the
    Orders application located here:

> [http:*//training.falafel.com/dynamiccontent*](http://training.falafel.com/dynamiccontent)

68. Select **File \| New \| Project\...** and on the **Create Project**
    dialog click the **OK** button.

69. Start recording a new test. From the Recorder toolbar, drop down the
    Low-Level Procedure button and select the **Record Low-Level
    Procedure (window coordinates)** option.

![](./media/image313.png){width="5.204438976377952in"
height="1.11375in"}

> **Figure 222 \--Recording a Low-Level Procedure**

70. A red selection rectangle will appear. Move the rectangle onto
    Internet Explorer and click the left mouse button to select it.

![](./media/image314.jpeg){width="2.1676990376202974in"
height="1.8046872265966754in"}

> **Figure 223 \--Selecting IE**

71. On the **Create Project Item** dialog click **OK** to add the
    **Low-Level Procedures Collection** item to the project.

![](./media/image315.png){width="4.311887576552931in"
height="2.0315616797900264in"}

> **Figure 224 \--Adding the Low-Level Procedures Collection**

72. On the **Create Project Item** dialog click **OK** to add a
    Low-Level Procedure to the project.

![](./media/image316.png){width="4.301522309711286in"
height="2.0315616797900264in"}

> **Figure 225 \--Adding a Low Level Procedure**

73. Select the **Add \| New \| Customer \| Orders** menu item on the web
    page.

![](./media/image317.png){width="3.5686811023622047in"
height="2.2395833333333335in"}

> **Figure 226 \--Selecting from a Dynamic Menu**

74. Click the **Stop** button on the recording toolbar.

#### Examining the Recording

> At the completion of the recording you can see that a \"LLCollection\"
> has been added in the Project Explorer. Inside the collection will be
> the Low-Level Procedure you recorded.

![](./media/image318.png){width="1.9227165354330709in"
height="1.3303116797900263in"}

> **Figure 227 \--The Low Level Procedure Collection**
>
> Next, look at the **Low Level Procedure Editor** and the events
> captured by the Low Level Procedure. Double click the **Advanced \|
> LLCollection1 \| LLP1** node from the **Project Explorer**.

![](./media/image319.png){width="3.6925984251968504in"
height="2.4791666666666665in"}

> **Figure 228 \--Low Level Procedure Editor**
>
> The columns in the Low-level Procedure Editor are:

  **Column**   **Value**
  ------------ ------------------------------------------
  **Icon**     Indicator of the type of event performed
  **N**        Ordinal value of this event in the list
  **Event**    Type of action to be performed

  **Column**       **Value**
  ---------------- --------------------------------------
  **Parameters**   Data specific to the specified event
  **Delay, ms**    Delay in milliseconds between events

> From the Low-level Procedure Editor window, you can add, edit and
> delete events from the list using the right click context menu.

![](./media/image320.png){width="3.6925984251968504in"
height="2.4791666666666665in"}

> **Figure 229 \--The Editor Window Context Menu**
>
> The Edit Event dialog provides options to customize all facets of the
> captured event.

![](./media/image321.png){width="2.61334864391951in"
height="1.8459372265966754in"}

> **Figure 230 \-- The Edit Event Dialog**

Calling Low Level Procedures from Script
----------------------------------------

> To run a Low Level Procedure from a Keyword Test, first specify the
> collection followed by a period \".\", then the name of the low level
> procedure, another period \".\" and finally the **Execute()** method.
> If you want the low-level procedure to execute in relation to a
> particular window, pass the window as a parameter to the Execute
> method. Also notice in the example below that before executing the
> low-level procedure, you want to make sure that the window is
> activated and brought to the front.
>
> **var** iexplore = Aliases.iexplore.IEFrame; iexplore.Activate();
> LLCollection1.LLP1.Execute(iexplore);
>
> **Dim** iexplore = Aliases.iexplore.IEFrame iexplore.Activate()
> LLCollection1.LLP1.Execute(iexplore)

Summary
-------

> In this chapter, we looked at TestComplete Low Level Procedure
> capabilities and: Explained how this recording type differs from a
> standard object-based recording Recorded a scenario which otherwise
> requires special handling
>
> Examined the Low-Level Procedure Editor

### User Forms

User Forms
==========

Objectives
----------

> This chapter demonstrates how User Forms are used to display dialogs
> and windows onscreen during test execution. You\'ll learn how to use
> the TestComplete User Form\'s designer to create your own forms.
> You\'ll also see how modal and non-modal display modes manage form
> display during test execution.

[]{#Materials .anchor}

> **Using the Designer**
>
> User Forms are not part of the default project template so you\'ll
> first need to add the **User Forms** Project Item to your project.
> Once you\'ve added User Forms support to your project you can right
> click the User Forms node in the Project Explorer and add a form to
> your project. In this example, we\'ll construct a User Form that can
> be used to prompt for login credentials.

![](./media/image322.png){width="2.613190069991251in"
height="1.8356244531933508in"}

> **Figure 231 \--User Form s Login Dialog**
>
> Once the form is created you will see the User Forms designer which is
> similar in style to those seen in Visual Basic, Visual Studio or other
> development tools supporting forms development. If you are familiar
> with any of these tools you\'ll immediately feel right at home in the
> designer. If not, don\'t fear. Learning the designer is quick and easy
> and you\'ll be able to construct dialogs in no time.

#### Layout of the User Forms Designer

> There are three panels of the User Forms editor including:

75. Component palette

76. Form Designer

77. Properties window

![](./media/image323.png){width="5.950223097112861in"
height="3.9459372265966755in"}

> **Figure 232 \--User Forms Editor**

#### Building a User Form

> To illustrate the functionality of the User Forms designer we\'ll
> build a Login dialog that you can call from within your tests. If the
> UserForms node doesn\'t already exist in the project explorer,
> right-click the project and select **Add \| New Item**. Choose \"User
> Forms\" from the list and click **OK** to create the project item.

![](./media/image324.png){width="4.3459667541557305in"
height="3.5833333333333335in"}

> **Figure 233 \--Adding User Forms**
>
> To create the form, right click the Project Explorer **UserForms**
> node and select **Add \| New Item\...** In the **Name** edit box enter
> \"PasswordDlg\".

![](./media/image325.png){width="4.312343613298338in"
height="1.9903116797900262in"}

> **Figure 234 \--Adding a User Form**
>
> Using the Component palette, we\'ll add the components (TcxTextEdit,
> TcxLabel and TcxButton) from the **Editors**, **Helpers** and
> **Buttons** categories respectively to the form by simply double
> clicking the components. After adding a component to the design-time
> form you can use the mouse to move/size the control and the Properties
> window to change its appearance/behavior. We now have a form that
> looks like this:

![](./media/image326.png){width="5.926007217847769in"
height="2.900624453193351in"}

> **Figure 235 \--Initial User Forms Layout**
>
> Next, we need to make the following property changes on the components
> placed on the form. The table below lists the components and the
> property/values for each. These changes improve the appearance of the
> dialog as well as set the expected behavior of a modal login dialog.

  **Component**   **Property**          **Value**
  --------------- --------------------- -------------
  cxTextEdit1     Name                  edUsername
                  Text                  (blank)
  cxTextEdit2     Name                  edPassword
                  Text                  (blank)
                  Properties.EchoMode   eemPassword
  cxLabel1        Caption               &Username:
                  FocusControl          edUsername

  **Component**   **Property**   **Value**
  --------------- -------------- ------------
  cxLabel2        Caption        &Password
                  FocusControl   edPassword
  cxButton1       Caption        OK
                  Default        True
                  ModalResult    mrOk
  cxButton2       Caption        Cancel
                  Cancel         True
                  ModalResult    True
  \[User Form\]   Caption        Login

> Once these properties have been assigned we\'ll have a completed User
> Form that we can use from within a Keyword Test.

![](./media/image327.png){width="5.915184820647419in"
height="3.1755205599300087in"}

> **Figure 236 \--The Com pleted Form**
>
> []{#Calling_User_Forms_from_Script .anchor}**Calling User Forms from
> Script**
>
> Now that we have created a user form, we need to learn how to call the
> form from Script. There are two method used to display a user form:
> **Show()** and **ShowModal()**.
>
> ShowModal() displays the user form and stops the script from playing
> until the user answers the dialog. Show() continues with the next line
> in the script code.
>
> *//Fill in the current user name*
> UserForms.UserNameAndPassword.edtUser.Text = Sys.UserName; **if**
> (UserForms.UserNameAndPassword.ShowModal() == mrCancel)
>
> Runner.Halt(\"User Cancelled Test\");
>
> Log.Message(\"User: \" + UserForms.UserNameAndPassword.edtUser.Text +
> \" Logged in with Password: \" +
> UserForms.UserNameAndPassword.edtPassword.Text);
>
> *\'Fill in the current user name*
> UserForms.UserNameAndPassword.edtUser.Text = Sys.UserName **if**
> UserForms.UserNameAndPassword.ShowModal = mrCancel **Then**
>
> Runner.Halt(\"User Cancelled Test\")
>
> **end If**
>
> **Log**.Message(\"User: \" &
> UserForms.UserNameAndPassword.edtUser.Text &\_ \" Logged in with
> Password: \" &\_ UserForms.UserNameAndPassword.edtPassword.Text)
>
> []{#_bookmark318 .anchor}**Summary**
>
> In this chapter, we learned how to create user forms for input during
> test execution. We learned about the User Forms designer and how to
> incorporate user forms into a test.

### Best Practices

18. []{#Best_Practices .anchor}**Best Practices**

> **Objectives**
>
> This chapter includes real-world advice on how to plan, organize and
> version control your tests. Other handy tips tell you how to get the
> most out of \"smoke tests\" and how to communicate your test results
> with the team.
>
> []{#Communicating_Test_Results .anchor}**Communicating Test Results**
>
> Now you might be thinking \"huh? I haven\'t even started yet and I
> have to think about communicating my results?\" The answer is a
> resounding YES! Unfortunately, Quality Assurance and test automation
> specifically, at least in the software world, tends to get a bad rap.
> Creating solid test automation that can stand up over time and provide
> valuable ongoing feedback is a difficult task which leads a lot of
> people (read management) to think time and effort spent working on
> automation is wasted.
>
> To solve this problem, you'll want to focus on getting your test
> results published quickly and consistently to prove that your efforts
> are worth the investment. TestComplete provides some facilities for
> producing log output though you'll want to be sure and iron out your
> strategy from the start. For example, you may want to setup a web
> server where you can publish results. In fact, TestComplete supports
> exporting log results to HTML which could be a good starting place.
>
> []{#Plan_your_testing,_but_not_that_kind_of_ .anchor}**Plan your
> testing, but not that kind of planning\...**
>
> The preparation we\'re referring to has to do with your choice of
> testing tool, TestComplete. Although it\'s important to plan the
> application features to be tested, it\'s also important to be prepared
> with respect to the testing facilities available in TestComplete. You
> should gain a thorough understanding of TestComplete features before
> you embark on writing test automation to avoid a situation where your
> weeks into test development only to discover a feature that could have
> saved you numerous hours or days.
>
> TestComplete is rich with features that make test automation easier
> although like any development tool it provides many different ways to
> solve the same problem. For example, TestComplete has a powerful and
> indeed almost alluring recorder, making it easy to quickly create
> automated tests. While a test recorder is a great tool, recorded tests
> tend to be more brittle than hand written tests because they capture a
> single iteration at a given point in time and don\'t take into account
> unexpected events like an error dialog popping up. The alternative is
> handwritten tests where you can methodically plan how the test will
> react in unexpected circumstances. The down side of handwritten tests
> is they tend to take longer to develop though over the long run
> they\'ll likely require less maintenance because of the tendency to
> design the test more rigorously.
>
> []{#Organizing_your_TestComplete_Projects .anchor}**Organizing your
> TestComplete Projects**
>
> TestComplete provides the ability to customize the Project Items that
> are included by default on a new project using Project Templates. In
> order to maintain consistency across your testing organization you
> should work towards creating a project template(s) that\'s
> pre-configured for your test environment. For example, if you\'re
> testing a Window 32-bit GUI application, create a Project Template
> that has the Tested Applications node with your application already
> added to it. Also, look closely at how you can utilize Aliases to
> avoid using long dotted object names like:
>
> Sys.Process(\"iexplore\").IEFrame(0).Window(\"WorkerW\", \"\",
> 1).Window( \"ReBarWindow32\", \"\", 1).Window(\"ComboBoxEx32\", \"\",
> 1).Window(
>
> \"ComboBox\", \"\", 1).Window(\"Edit\", \"\", 1)
>
> TestComplete includes an automatic Name Mapping feature has been added
> to make this even easier.
>
> []{#Use_a_Source_Control_Repository .anchor}**Use a Source Control
> Repository**
>
> TestComplete is a development tool and as such the projects, scripts,
> data, etc. used in your tests should be kept under version control. If
> this is something you\'re already doing, skip ahead. If not, you
> should consider version control the next priority and work to get your
> test suites under version control. There are lots of options including
> some excellent Open Source projects which are freely available like
> Subversion, otherwise known as SVN. While it\'s beyond the scope of
> this document to discuss the specific merits of source control it\'s a
> subject that shouldn\'t be ignored.
>
> []{#Your_Most_Important_Test .anchor}**Your Most Important Test**
>
> Arguably, the first test you should focus on is a \"smoke test\". In
> this section we\'ll discuss what a smoke test is and provide guidance
> as to how to construct the test in such a way as to maximize its
> effectiveness.

#### Creating a Smoke Test

> Probably the most important test you\'ll write is your Smoke Test, at
> least it should be. Typically, the goal of a Smoke Test is to verify
> that the latest build delivered to QA is either worth further
> consideration or \"DOA\" (dead on arrival). The smoke test is crucial
> because of the time savings it can provide both R&D and QA. A good
> Smoke Test should:
>
> Run quickly \-- a smoke test should not last for hours but minutes and
> test the most crucial functionality.
>
> Fail quickly \-- as soon as a failure is detected in the smoke test
> should end and trigger a failure notification.
>
> Cover a broad range of functionality, focusing on breadth not depth.
> Require minimal setup/configuration of the application under test. Be
> setup to run against every build.
>
> Adapt over time as the application under test evolves. Serve as a
> model for new test automation.
>
> If you take the time to organize your Smoke Test to cover these goals
> you will undoubtedly save time and resources over the long run. Your
> Smoke Test should serve as a model that embodies your \"best
> practices\" from which your QA team can draw from for their own tests.
>
> If you\'ve never written a Smoke Test before, start small. In the
> beginning simply get the smoke test to verify even a single piece of
> functionality consistently. Over time, work to increase its coverage
> but remain focused on the quality of the test. It\'s unacceptable to
> have a Smoke Test that can\'t run consistently and without problems.

#### Executing your Tests Regularly

> Once your Smoke Test is written and under version control the next
> step is to automate its execution. SmartBear has a product called
> Automated Build Studio which can automate your TestComplete tests and
> trigger them to execute when a new build is delivered to QA, a process
> called **Continuous Integration** or **\"CI\"**. In addition to
> Automated Build Studio there are Open Source CI servers such as
> CruiseControl.NET.
>
> The main benefit of a CI server is to reduce the amount of time it
> takes to execute your test automation as well as ensure that it
> executes against every build. By setting up a CI server you can not
> only free your QA engineers from having to manually execute their
> tests. CI helps quickly identify tests that are unable to consistently
> run to completion and may require closer scrutiny. In addition, many
> CI servers include a means of publishing test results providing for
> greater visibility into the automation efforts.
>
> []{#General .anchor}**General**
>
> The following are general tips and best practices to help you get the
> most out of TestComplete:
>
> Record/Playback is a quick and easy way to get automated tests up and
> running but tend to be brittle leading to problems when the
> application changes, etc.
>
> Use the TestItems of the project as a framework for Test Cases (see
> the \"Project Organization\" chapter).
>
> Separate Data from the Test Framework (see \"Data Driven Testing\").
>
> Use the code metrics of the Code Explorer to improve the quality of
> the script code (see Overview of TestComplete).
>
> Use reusable routines whenever possible (see the \"Project
> Organization\" chapter). Keep routines short, i.e. less than a page of
> code.
>
> Use meaningful variable names. The default variable names of a
> recording are not acceptable for production use.
>
> []{#Web_Page .anchor}**Web Page**
>
> The following are tips for making effective use of TestComplete when
> testing web pages:
>
> Make sure that \"Make the Page object a child of the browser process\"
> is selected in the Project properties under **Open Applications \| Web
> Testing**.
>
> Use the \"Tree Model\" for best performance. You can set this under
> the Project properties in the General options.
>
> []{#Summary .anchor}**Summary**
>
> In this chapter you learned how to plan, organize and version control
> your tests. You also reviewed tips on how to get the most out of
> \"smoke tests\" and how to communicate your test results with the
> team.

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