### User Forms

Objectives
----------

> This chapter demonstrates how User Forms are used to display dialogs
> and windows onscreen during test execution. You\'ll learn how to use
> the TestComplete User Form\'s designer to create your own forms.
> You\'ll also see how modal and non-modal display modes manage form
> display during test execution.

#### Using the Designer
>
> User Forms are not part of the default project template so you\'ll
> first need to add the **User Forms** Project Item to your project.
> Once you\'ve added User Forms support to your project you can right
> click the User Forms node in the Project Explorer and add a form to
> your project. In this example, we\'ll construct a User Form that can
> be used to prompt for login credentials.

![](../media/image322.png)

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

![](../media/image323.png)

> **Figure 232 \--User Forms Editor**

#### Building a User Form

> To illustrate the functionality of the User Forms designer we\'ll
> build a Login dialog that you can call from within your tests. If the
> UserForms node doesn\'t already exist in the project explorer,
> right-click the project and select **Add \| New Item**. Choose \"User
> Forms\" from the list and click **OK** to create the project item.

![](../media/image324.png)

> **Figure 233 \--Adding User Forms**
>
> To create the form, right click the Project Explorer **UserForms**
> node and select **Add \| New Item\...** In the **Name** edit box enter
> \"PasswordDlg\".

![](../media/image325.png)

> **Figure 234 \--Adding a User Form**
>
> Using the Component palette, we\'ll add the components (TcxTextEdit,
> TcxLabel and TcxButton) from the **Editors**, **Helpers** and
> **Buttons** categories respectively to the form by simply double
> clicking the components. After adding a component to the design-time
> form you can use the mouse to move/size the control and the Properties
> window to change its appearance/behavior. We now have a form that
> looks like this:

![](../media/image326.png)

> **Figure 235 \--Initial User Forms Layout**
>
> Next, we need to make the following property changes on the components
> placed on the form. The table below lists the components and the
> property/values for each. These changes improve the appearance of the
> dialog as well as set the expected behavior of a modal login dialog.

  |**Component**   |**Property**          |**Value**|
  |---|---|---|
  |cxTextEdit1     |Name                  |edUsername|
  |                |Text                  |(blank)|
  |cxTextEdit2     |Name                  |edPassword|
  |                |Text                  |(blank)|
  |                |Properties.EchoMode   |eemPassword|
  |cxLabel1        |Caption               |&Username:|
  |                |FocusControl          |edUsername|
  |cxLabel2        |Caption        |&Password|
  |                |FocusControl   |edPassword|
  |cxButton1       |Caption        |OK|
  |                |Default        |True|
  |                |ModalResult    |mrOk|
  |cxButton2       |Caption        |Cancel|
  |                |Cancel         |True|
  |                |ModalResult    |True|
  |\[User Form\]   |Caption        |Login|

> Once these properties have been assigned we\'ll have a completed User
> Form that we can use from within a Keyword Test.

![](../media/image327.png)

> **Figure 236 \--The Com pleted Form**
>
#### Calling User Forms from Script
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
#### Summary
>
> In this chapter, we learned how to create user forms for input during
> test execution. We learned about the User Forms designer and how to
> incorporate user forms into a test.