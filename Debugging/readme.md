### Debugging

#### Objectives
>
> This chapter demonstrates the debugging features of TestComplete that
> allow you to locate and fix bugs in your tests. Along the way you\'ll
> learn how to start a test in the debugger, use the various debugger
> windows and how to work with breakpoints.
>
#### Debugging Tests
>
> The debugger capabilities in TestComplete help track down script
> errors, flow problems and also to evaluate the values of local and
> global variables. TestComplete has its own debugger built-in, so you
> don\'t need to install any other software. Note: You may need to set a
> breakpoint to use the debugger, otherwise the test may finish running
> before stopping anywhere in the code. See the Breakpoints topic for
> more information.

#### Test Engine Toolbar

> You can use the **Run** button on the Test Engine toolbar to start
> debugging a test. To use the **Run** button from the toolbar you must
> have a **Project Item** defined otherwise TestComplete will prompt you
> to create one. Refer to the Project Organization chapter for
> information on project test Items.

![](../media/image151.png)

> **Figure 121 \--Test Engine Toolbar**

#### Debugger Toolbar

> You can also use the debugger toolbar buttons to run your debugging
> session.

![](../media/image152.jpeg)

> **Figure 122 \--Debug Toolbar**
>
> **Run to Cursor** \-- Runs the test up to the cursor and stops, just
> as if there had been a break point at the cursor location.
>
> **Step Into** \-- Executes the next step in the test. If another test
> or routine is called, the debugger continues on the first line of the
> test or routine.
>
> **Step Over** \-- Executes the next step in the test. If another test
> or routine is called, the debugger executes the entire call at once
> and continues on the next line after the test or routine.
>
> **Evaluation Dialog** \-- Opens the Evaluate Dialog. The dialog allows
> you to view and modify variables, expressions and objects.
>
> **Breakpoints, Watch List, Locals** and **Call Stack** \-- These
> buttons display panels of the same names and are described in the
> \"Exploring Debugger Panels\" topic.

#### Code Editor Context Menu

> The context menu for the Code Editor has several options related to
> debugging that are enabled depending on the option and if the script
> is currently running.

![](../media/image153.png)

> **Figure 123 \--Code Editor Context Menu**
>
> **Run Current Routine \--** Runs the routine under the mouse when the
> context menu is invoked.
>
> **Set Next Statement \--** When the script is running, you can place
> the starting point for the next statement on any line. Be aware that
> if you skip any setup code that is expected by following lines of
> code, such as the assignment of a variable value, that subsequent
> lines of code may fail.
>
> **Go to Error \--** This option jumps to the first line of code that
> has a syntax error.

![](../media/image154.png)

> **Figure 124 \--The Go To Error Option**
>
> **Debug \| Toggle Breakpoint \--** Toggles the breakpoint for the
> clicked line.
>
> **Debug \| Evaluate \--** Allows you to see the current value of an
> expression and to actually change the expression on-the-fly. The
> screenshot below shows the current value of the variable \"result\"
> plus one.

![](../media/image155.png)

#### Using the Evaluate Dialog
>
> **Debug \| Run to Cursor \--** Runs the script up to the cursor and
> stops, just as if there had been a break point where the cursor is.
>
> **Debug \| Add Watch \--** Adds a watch for the currently selected
> expression.
>
#### Exploring Debugger Panels
>
> TestComplete includes four different debug panel each of which
> provides useful feedback for debugging tests.
>
> **Breakpoints** \-- User defined list of steps where the debugger will
> halt test execution.
>
> **Watch List** \-- User defined list of variables to examine.
>
> **Locals** \-- Used to examine the values of locally defined
> variables.
>
> **Call Stack** \-- Used to view the current execution path of the
> test.

#### Breakpoints

> A breakpoint is a signal to the TestComplete debugger that you want to
> stop or \"break\" the execution of the test at the desired location.
> To place a breakpoint in your test, click in the gutter of the script
> line you wish to stop on. To remove a breakpoint, click the breakpoint
> icon in the gutter or delete it from the Breakpoints window. The
> screenshot below shows two breakpoints placed on lines 35 and 41. The
> Breakpoints window allows you to configure each breakpoint.

![](../media/image156.png)

> **Figure 125 \--Breakpoints in Script**
>
> In the Breakpoints panel you can:
>
> Enable or disable a specific breakpoint. That is better than deleting
> them and reentering them all over based on different debug sessions.
>
> View the Location of the unit name it resides in and also the line
> number of where it resides.
>
> Include a description to explain the goal behind using the breakpoint.
>
> Finally, you have two powerful features in the breakpoints window
> which are **Pass Count** and **Condition**. If you are debugging a
> \"For Loop\" that goes on for 1000 iterations, knowing that it will
> fail sometime after 900 times, it would be wise to place a Pass Count
> of 900 on the breakpoint instead of having to step over the breakpoint
> 900 times. When the pass count is not known but a condition has to be
> met, the Condition property can be set (e.g. x \> 100).

##### Lab: Conditional Breakpoints

> Conditional breakpoints can be very useful for controlling the
> execution of a debug session particularly when the test is performing
> a repetitive set of steps. By specifying either a **Pass Count** or a
> **Condition** you can control when a breakpoint will be \"hit\" (when
> test execution stops at the breakpoint) allowing you to skip loop
> iterations that are not significant to resolving an issue within the
> test.
>
> Let\'s build an example that executes a **For Loop** and where we only
> want execution to stop when the loop hits its 50th iteration.

24. Add the code below to a script unit.

> **function** LoopTest(){
>
> **var** i;
>
> **for**(i = 1; i \< 100; i++)
>
> {
>
> Log.Message(\"for loop message\");
>
> }
>
> }
>
> **Sub** LoopTest()
>
> **Dim** I
>
> **For** I = 1 **to** 100
>
> **Log**.Message(\"for loop message\")
>
> **Next End Sub**

25. Click the gutter of the editor on the Log Message step to place a
    breakpoint on the line then right click the breakpoint and select
    Properties\...

![](../media/image157.png)

> **Figure 126 \--Setting Breakpoint Properties**

26. On the Breakpoint Properties dialog enter \"50\" in the Pass count
    field and click **OK**.

![](../media/image158.png)

> **Figure 127 \--Setting the Pass Count**
>
> Your test should now look like the screenshot below. Notice that the
> graphic for the breakpoint has changed to indicate that it is
> conditional.

![](../media/image159.png)

> **Figure 128 \--Conditional Breakpoint**

27. Run the routine. When the editor breaks on Log.Message(), the Locals
    window will show the \"i\" variable with a value of \"50\".

![](../media/image160.png)

> **Figure 129 \--Test Stopped at Conditional Breakpoint**

#### Watch List Panel

> The **Watch List** panel is a read/write list of expressions you\'re
> interested in examining during the debug session. The Watch List is
> similar in function to the Locals panel though requires the user to
> manually specify values to inspect. Like the Locals Window, the list
> of expressions updates automatically as you debug your code. The Watch
> List allows you to specify any script expression for inspection
> including variables, object and mathematical expressions (such as A +
> B). Like the Locals view, the Watch List uses a tree structure,
> allowing you to see sub-properties of objects on the system that are
> used by your test.
>
> The screenshot below shows objects and properties with simple types
> (Boolean, String and Integer). The last watch is a mathematical
> expression \"count % 2\". See the online help for the language you are
> using to see what expressions can be included here. Also notice that
> the Value column may be highlighted to indicate that the value has
> changed.

![](../media/image161.png)

> **Figure 130 \--The Watch List**
>
> The three columns in the **Watch List** panel are:

  |**Column**      | **Description**|
  |---|---|
  |**Expression**   |The expression, variable, parameter, object or property to view while debugging. The checkbox appearing in this column controls whether or not the expression is evaluated. One reason to uncheck an expression is if it takes considerable time to evaluate and slows debugging|
  |**Value**        |The current value of the watch expression|
  |**Type**         |The data type of the variable being displayed|

##### Using the Watch Properties Dialog

> Unlike the Locals panel, the **Watch List** panel is read/write and
> provides the ability to specify how the information should be
> displayed. To modify a watch, either double-click the item in the
> **Watch** panel or select **Edit** from the context menu.

![](../media/image162.png)

> **Figure 131 \--Editing a Watch**
>
> This will display the watch Properties dialog allowing you to control
> the display of the value returned for the selected watch. For example,
> if the watch is on an integer value you can view the result as a
> Hexadecimal value.

![](../media/image163.png)

> **Figure 132 \--Editing Watch Properties**

##### Recommended Usage

> While the **Watch** panel is a very useful tool for debugging, here
> are a few usability tips that will help you make the most of this
> tool:
>
> Keep the total number of active \"watches\" to a reasonable number.
> TestComplete updates each object after each step, so tracking too many
> variables can slow debugging.
>
> Use the checkbox next to the expression to disable the evaluation of a
> watch while keeping it in the list for later use.
>
> Use the Locals panel to monitor values used within your test. The
> Locals panel works like an automatic Watch List without having to add
> watches explicitly. It\'s possible to position both the Watch List and
> the Locals Panel to be visible on the screen at the same time.

#### Locals Panel

> The **Locals** panel is a read only list of variables in scope at the
> current point of execution. The list is automatically maintained by
> TestComplete and updates as you debug your code, providing a
> convenient means of inspecting the values of the relevant local
> variables during a debug session. The Locals view uses a tree
> structure allowing you to \"see into\" variables which reference
> objects on the system and view their properties as well.

![](../media/image164.png)

> **Figure 133 \--Locals Panel**
>
> The three columns in the Locals panel are:

  |**Column**  | **Description**|
  |---|---|
  |**Name**     |Name of the variable|
  |**Value**    |The current value of the variable|
  |**Type**     |The data type of the variable being displayed|

#### Call Stack Panel

> The **Call Stack** panel is a read only list of the routines currently
> executing as part of the running test. The list displays entries in
> descending order, starting with the routine currently being debugged.
> This allows you to see and trace the execution path through your test
> and is only active when a test is executing.
>
> Double clicking items in the **Call Stack** panel will take you to
> either the Keyword Test Step or line of script depending on the test
> currently executing. The **Call Stack** can display both Keyword Tests
> and script routines together.
>
> In the screenshot below, the test that\'s being debugged,
> \"TestOrdersApplication\" calls \"Login()\" which in turn calls
> \"VerifyAuthentication()\".

![](../media/image165.png)

> **Figure 134 \--Call Stack Panel**
>
#### Summary
>
> In this chapter, we covered TestComplete debugging features. We looked
> at: Requirements for debugging tests using TestComplete.
>
> Methods for starting a debug session.
>
> Debugger windows including the Call Stack, Locals, Watch and
> Breakpoints.