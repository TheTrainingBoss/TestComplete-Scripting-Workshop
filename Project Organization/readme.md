### Project Organization

#### Objectives
>
> This chapter examines the Project Workspace Editor and in particular,
> Test Items. You will see how Test Items are used to organize tests
> into larger hierarchical groupings and how to execute a group of tests
> all at one time.
>
#### The Project Workspace Editor
>
> Although the Workspace Panel holds all the possible editors that can
> be opened by double-clicking nodes in the Project Explorer, the
> **Project Workspace Editor** is a \"key player\". Using the Project
> Workspace Editor, you can organize tests into lists that can be
> configured, executed and logged as one entity under the **Test Items**
> tab.
>
> The Project Workspace Editor displays in the Workspace Panel when you
> open a project in the Project Explorer. Other tabs let you define
> variables available to the entire project, track issues, look at the
> logs for the project and define properties.

#### Test Items

> Use Test Items to reuse tests and to organize tests into larger
> groups. The Project Workspace Editor also controls how many times each
> test executes and how TestComplete should react if an error occurs.
>
> The screenshot below shows that both keyword and script tests can be
> organized into nested folders, renamed with friendly names and
> configured. The Test Items tab in the screenshot below shows a \"Smoke
> Tests\" group that contains an \"Order Entry\" group. Inside the
> \"Order Entry\" group is yet another group called \"Create Order\"
> that contains both keyword and script tests. Notice that you can place
> tests and/or groups at any level.

![](./media/image56.png)

> **Figure 43 \--The Project Workspace Editor**
>
> If you click the **Run Project** button from the main toolbar, a
> dialog like the one in the screenshot below may display complaining
> that there are no \"test items\". This dialog is telling you that you
> need to navigate to the project\'s Test Items and add tests.

![](./media/image57.png)

> **Figure 44 \--The \"no selected test items\" Dialog**

##### Adding Test Items

> Add items to the Test Items grid by either dragging tests from the
> Project Explorer, using the context menu or the toolbar. The
> screenshot below shows a script test being dragged and added as a Test
> Item.

![](./media/image58.png)

> **Figure 45 \--Adding Tests**
>
> You can only drag script units that contain at least one function and
> that have no syntax errors. Dragging a script unit to the test Items
> area includes all the functions within that unit. To be more
> selective, click the **Test** column and choose a single function for
> that test item.

##### Test Items Columns

> Each line in the Test Items grid represents either a folder or a test.
> You can disable an item from being run by unselecting the checkbox.
> This prevents the item and any of its children from running.

![](./media/image59.png)

> **Figure 46 \--Column Headings**
>
> **Name** \-- The friendly name of the test item as it will appear in
> the log.
>
> **Test** \-- The name of the test for that Test Item. This can be a
> keyword test, script, low level procedure etc.
>
> **Count** \-- The number of times the Test Item will run. By default,
> the value for this column is one. Use the up-down arrows in the column
> to adjust the count.
>
> **Timeout** \-- The maximum number of minutes the test item can run
> before timing out, generating an OnTimeout event and posting an error
> message in the log. Use the up- down arrows in the column to adjust
> the timeout.
>
> **Parameters** \-- This column lists parameters passed to the Test
> Item. The parameters are picked up automatically when a test is
> assigned. Click the ellipses in the column to display the **Test
> Parameters** dialog where you can adjust the **Value** for each
> parameter.

![](./media/image60.png)

> **Figure 47 \--Test Item Parameters**
>
> **Description** \-- A user friendly description of the Test Item.
>
> **Stop on Error**, **Stop on Exception** \-- You can specify the
> behavior of a test item after an error or exception. \"Errors\" can
> occur during the execution of script code and \"exceptions\" can occur
> in the application under test. The possible options you can choose
> from the drop-down list in the columns are \"None\" to ignore the
> error or exception and continue, \"Project\" to stop execution of the
> entire project if an error or exception occurs and \"Test Item\".
> \"Test Item\" is the default and stops execution for the current item
> and its children but allows the sibling items and higher to continue.
>
> By default, **Stop on Error** and **Stop on Exception** columns don\'t
> appear. To add them, right-click the Test Items grid and select Field
> Chooser from the context menu. The Customization dialog will appear
> with any columns that aren\'t showing. Drag columns to the grid
> heading, watching for the arrow indicators to show where the column
> will be inserted. You can also remove columns by dragging them back to
> the Customization dialog.

![](./media/image61.png)

> **Figure 48 \--Adding Columns**

##### Test Items Toolbar

> The toolbar and context menu for the Test Items area have roughly the
> same options that allow you to build the structure of the Test Items
> tree view.

![](./media/image62.jpeg)

> **Add Child Test Item \--** Adds a child test item just below the
> selected item. You can use the context menu to add a new top-level
> item.
>
> **Add Group \--** Adds a top-level folder that can contain other
> folders and tests.
>
> **Add Subgroup \--** Add a child folder under the selected test item.
>
> **Delete \--** Remove the selected item permanently.
>
> **Run Selected \--** Run the selected test item and any children.
>
> **Jump to Test \--** Open up the keyword or script test.
>
> **Move Items \--** Move test items up/down/indent/outdent in the list.
>
> **Enable/Disable \--** Enable or disable items. Options from
> left-to-right are Enable All, Disable All, Toggle All, Enable Selected
> and Disable Selected.

#### Variables

> The **Variables** tab of the Project Workspace Editor allows you to
> define **Temporary Variables** that are active only during one test
> run and **Persistent Variables** that are available between tests
> runs.

![](./media/image63.png)

> **Figure 49 \--Variables**
>
> **Name** \-- The name of the variable. The name must be alpha-numeric,
> must not contain spaces and must start with an alpha character. If
> these naming rules are not followed, Name entry reverts to its
> previous contents when you press enter.
>
> **Type** \-- The type of data that will be stored in the variable.
> Both Persistent and Temporary variables can store Integer, Double,
> String and Boolean types. Temporary variables can also store Object,
> DB Table and Table types.
>
> **Default Value** \-- The value when the project is first opened on a
> remote computer.
>
> **Local Value** \-- The current value of the variable on the computer
> where the project is opened. The Local Value column is only available
> for Persistent variables.
>
> **Description** \-- A user friendly description of the variable.
>
> **Category** \-- An arbitrary category that you can assign to make it
> easy to sort and filter variables. This column is not visible by
> default. Use the Field Chooser option on the context menu to view this
> column.

#### Issue Tracking Templates

> The Issue Tracking Templates tab allows you to establish connections
> to a bug tracking system such as Visual Studio Team System or Bugzilla
> and have TestComplete post results directly to those systems.
>
#### Lab
>
> In this Lab you will use Test Items to build a \"Smoke Test\" from
> other tests.

5.  Create a new project called \"MyProject\".

6.  Create four Keyword tests and name them \"Login\", \"Logout\",
    \"AddOrderHeader\", \"AddOrderDetail\". You can use Keyword Tests or
    Script tests. If you use Script, you must place at least one
    function in each so they will be recognized by the Project Test Item
    editor.

7.  Double-click the \"MyProject\" node in the Project Explorer.

8.  In the Test Items window, click the **Add New Group** button on the
    toolbar. Click the group and rename it \"Smoke Test\".

![](./media/image64.png)

> **Figure 50 \--Adding and Renaming a Group**

9.  Click the **Add Subgroup** button and rename the subgroup \"Order
    Entry\".

![](./media/image65.png)

> **Figure 51 \--Adding and Renaming a Subgroup**

10. From the Project Explorer, drag the \"Login\" test and drop it on
    the \"Order Entry\" group.

![](./media/image66.jpeg)

> **Figure 52 \--Adding a Test**

11. Click the \"ProjectTestItem1\" and rename the test item \"Login\".

12. Repeat dragging tests \"AddOrderHeader\", \"AddOrderDetail\" and
    \"Logout\" to the \"OrderEntry\" subgroup and name them \"Add Order
    Header\", \"Add Order Detail\" and \"Logout\", respectively. The
    Test Items should now look like the screenshot below.

![](./media/image67.png)

> **Figure 53 \--Project Test Items**

13. Click the **Run Project** button from the TestComplete toolbar.

![](./media/image68.png)

> **Figure 54 \--Running the Project**

14. When the test completes, the test log will display. Notice that the
    structure of the log matches the structure of the test items.

![](./media/image69.png)

> **Figure 55 \--Test Log**
>
#### Summary
>
> In this chapter you examined the Project Workspace Editor and in
> particular, Test Items. You saw how Test Items are used to organize
> tests into larger hierarchical groupings and how to execute a group of
> tests all at one time.