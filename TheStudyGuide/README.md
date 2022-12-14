# Study Guide Here
Everything is in the UiPath exam documentation and from the UiPath Associate Learning Plan on the UiPath website. This study guide does not guarantee to pass the exam. 

## Exam Sections

### Robotic Process Automation (RPA) Fundamentals

> Describe the processes suitable for automation and the processes executed with the different robot types; for example, attended verses unattended

#### Attended Robot
* Help individual users with small repetitive tasks
* Processes are triggered by users or specific user events (e.g. _a call is received_)
* Runs on the same machine on which the user performs the tasks

#### Unattended Robot
* Runs long processes or automations without human interaction
* Not dependent on users to trigger processes, as they are controlled through Orchestrator
* Runs on any machine connected to Orchestrator, usually dedicated machines are used

##### Reference
[https://docs.uipath.com/robot/docs/attended-vs-unattended](https://docs.uipath.com/robot/docs/attended-vs-unattended)

---

> Explain the functionality and interactions of UiPath products; Studio, Orchestrator, and Assistant

#### UiPath Studio Interface

##### The Designer Panel
* Used to design automation projects by dragging and dropping activities into it.

##### The Project Panel
* Displayed as a tree structure, where the root node is the name of the project and the branches contain the dependencies, inputs, settings and project files

##### The Activities Panel
* Helps you select the right activity to be added to your automation.

##### The Properties Panel
* To manage the properties of various activities and to manage variables.

##### The Variables Panel
* Enables you to create variables and make changes to them

##### The Arguments Panel
* Used when accessing a workflow to pass input through an argument or get the output from an argument or input/output from an argument.

##### The Output Panel
* To verify the results of the workflow using log messages or writing line activities

##### The Outline Panel
* Used to view the hierarchy of the selected workflow and all nodes available inside the workflow

#### UiPath Orchestrator
* Manages all the published automation solutions developed in Studio
* Execute of tasks by robots
* Execute schedules

**Capabilities**
* Provisioning
* Deployment
* Configuration
* Monitoring
* Queues
* Integrated Connectivity
* Version Control

#### UiPath Robots
* Are known as execution agents, execute the workflows created in UiPath Studio.

##### Robot Types
* Standard
* Floating

1. Attended
2. Unattended
3. Development
4. Non-Production

### UiPath Studio Overview
> Explain the debug functions and how they are used; for example, using Breakpoints

#### What is Debugging?

The process of identifying and resolving errors that prevent the project from functioning correctly. It is recommended to perform debugging during the design stage of the automation project, at activity, file and project level. By default, debugging is performed on the local robot.

##### Reference
[https://docs.uipath.com/studio/docs/about-debugging](https://docs.uipath.com/studio/docs/about-debugging)

#### Start Debugging

The options for running and debugging a file or project are available in the Design and Debug tabs.

* Debug         :   Click Debug or use `F5` to debug the whole project.
* Run           :   Click Run or use `Ctrl + F5` to run the whole project.
* Debug File    :   Click Debug File or use `F6` to debug the current file.
* Run File      :   Click Run File or use `Ctrl + F6` to run the file.
* Stop          :   Click the Stop or use `F12` to exit debug mode and return to design mode.

Note that the default action of the Play button in the Ribbon is Debug Current File.

#### The Debugging Panel

The debugging actions located on both the Design or Debug ribbon tabs. However, the debugging process is not available if project files have validation errors

* Step Into
    * Used to debug activities one at a time
    * When triggered, the debugger opens and highlights the activity before it is executed
    * When used with Invoke Workflow File activities, the workflow is opened in a new tab in `ReadOnly` mode and each activity is executed one by one
    * The keyboard shortcut for Step Into is `F11`
* Step Over
    * Does not open the current container
    * When used, the action debugs the next activity, highlighting containers (such as flowcharts, sequences, or Invoke Workflow File activities) without opening them
    * Comes in handy for skipping analysis of large containers which are unlikely to trigger any issues during execution
    * The keyboard shortcut for Step Over is `F10`
* Step Out
    * This action is used for stepping out and pausing the execution at the level of the current container
    * Completes the execution of activities in the current container, before pausing the debugging
    * This option works well with nested sequences
    * The keyboard shortcut for Step Out is `Shift + F11`
* Retry
    * Re-executes the previous activity, and throws the exception if it's encountered again
    * The activity which threw the exception is highlighted and details about the error are shown in the `Locals` and `Call Stack` panels
* Ignore
    * Ignore an encountered exception and continue the execution from the next activity so that the rest of the workflow can be debugged
    * Useful when jumping over the activity that threw the exception and continuing debugging the remaining part of the project
* Restart
    * Available after the exception was thrown and the debug process is paused
    * The action is used for restarting the debugging process from the first activity of the project
    * Use `Slow Step` to slow down the debugging speed and properly inspect activities as they are executed
    * When using this option after using the `Run from this Activity` action, the debugging is restarted from the previously indicated activity
* Break
    * Allows you to pause the debugging process at any given amount
    * The activity which is being debugged remains highlighted when paused
    * While paused, you can choose to Continue, Step Into, Step Over, or Stop the debugging process
    * Recommended to use `Break` along with `Slow Step` so that you know exactly when the debugging needs to be paused
* Focus
    * Helps you return to the current breakpoint or the activity that caused an error during debugging
    * The Focus button is used after navigating through the process, as an easy way to return to the activity that caused the error and resume the debugging process
    * When debugging is paused because a breakpoint was reached:
        * `Focus` can be used for returning to said breakpoint, after navigating through activities contained in the automation process
    * When the debugging is paused either after using `Step Into` or `Step Over` and then navigating through the process:
        * `Focus` returns to the activity that paused the debugging process
    * From the `Breakpoints` context menu:
        * You can select `Focus` to highlight the activity with the breakpoint
* Slow Step
    * Enables you to take a closer look at any activity during debugging
    * While enabled, activities are highlighted in the debugging process
    * Containers such as flowcharts, sequences, or Invoke Workflow File activities are opened
    * Similar to using `Step Into`, but without having to pause the debugging process
    * Can be activated both before or during the debugging process
    * Does not pause debugging
    * The action comes with 4 different speeds:
        * The selected speed step runs the debugging process slower than the previous one
        * Debugging with Slow Step at 1x runs it the slowest, and fastest at 4x
        * The speed dictates how fast the debugger jumps from one activity to the next
        * Each time you click `Slow Step` the speed changes by one step
* Execution Trail
    * The `Execution Trail` ribbon button is disabled by default
    * When enabled, it shows the exact execution path at debugging
    * As the process is executed, each activity is highlighted and marked in the `Designer` panel, showing you the execution as it happens:
        * Executed activities are marked and highlighted in green
        * Activities that were not executed are not marked in any way
        * Activities that threw an exception are marked and highlighted in red
* Highlight Elements
    * If enabled, UI elements are highlighted during debugging
    * The option can be used both with regular and step-by-step debugging
* Log Activities
* Continue on Exception
* Picture in Picture
* Remote Debugging
* Open Logs

#### Testing Activities

#### Locals Panel

#### Call Stack Panel
* The Call Stack panel displays the next activity to be executed and its parent containers when the project is paused in debugging
* The panel is displayed during execution in debug mode and it gets populated after using Step Into, Break, Slow Step, or after the execution was paused because an error or a breakpoint was encountered

#### Breakpoints Panel
* Breakpoints are used to purposely pause the debugging process on an activity which may trigger execution issues
* Setting a condition and/or hit count turns the simple breakpoint to a conditional breakpoint
* Adding logging results turns the conditional breakpoint in a conditional tracepoint
* Adding only a logging message transforms the breakpoint to a simple tracepoint

#### Watch Panel

#### Immediate Panel
* The Immediate panel is only visible during debugging
* Can be used for inspecting data available at a certain point during debugging

---

> Identify how to manage dependencies

#### Adding Dependencies
1. Click on Manage Packages in the Design ribbon tab
2. In Project Dependencies, click on All Packages
3. Click on Local
4. Click on Download/Install package
5. Click Save

#### Updating Dependencies
1. Click on Manage Packages in the Design ribbon tab
2. In Project Dependencies, under Version click on Update
3. Click Save

---

> Understand the significance of connecting an automation project to a version control solution

#### What are version control systems?
* They are tools used by software development teams to manage the collaboration on large projects
* Developing larger projects that require collaboration between multiple users
* Allows developers to track a code change, review the history of the code, and revert to a previous version of the project, if needed

**Benefits**
* Enhanced collaboration                : Team members can work freely on any file at any time and merge the changes into a common version at the right time
* Storing versions                      : Only the current version is stored on the disk, all the others are in the system
* Restoring previous versions           : Restore older versions of the file at any time
* Tracking different project versions   : New versions are usually saved with change descriptions. Versions of the same file can also be compared

**Version Controls Available**
* GIT   :   distributed version control system
* TFS   :   centralized version control system
* SVN   :   centralized version control system

#### How to connect to a version control system
1. Go to Home ribbon tab
2. Select Tools
3. Select Plugins
4. Choose Enable

#### GIT
**Cloning a Remote Git Repository**
1. In Team tab, select Clone Repository
2. Select either Use HTTPS or Use SSH
3. Type the Repository URL, and choose an empty Check out directory
4. Select Use Credentials / Use Key
5. Click Open
6. In the Open window, select a project.json file to open in Studio

* Push      :   Will send the changes to the remote repository
* Pull      :   Will get the latest version from the remote repository
* Undo      :   Will revert the changes done after the last commit
* Commit    :   Will save the changes to the local repository

### UiPath Studio ??? Variables and Arguments

> Describe the different variables' types, how they are used, managed, and the best practice for using the variable scope

#### Variables
* Variables are containers that can hold multiple data entries (values) of the same data type
* The value of a variable can change through an external input, data manipulation, or passing from one activity to another
* Used to store multiple types of data

#### Create Variables
1. Press `Ctrl + K` in an activity input field that requires a variable
2. Select the `Create Variable` option in the Variables panel
3. Press `Ctrl + K` in an input field that requires a variable in the Properties panel
4. By performing right-click in the input field and selecting the `Create Variable` option

##### Reference
[https://docs.uipath.com/studio/docs/managing-variables](https://docs.uipath.com/studio/docs/managing-variables)

#### Variable Properties
1. Name:    Defines how the variable will be identified
2. Type:    Defines what kind of data can be stored in the variable
3. Scope:   Defines the part of the workflow where the variable can be used
4. Default: Defines the value the variable is initialized with

#### Variable Types

1. String
    * A text or string variable is a type of variable that can store only strings
    * Can be used to store any information such as employee names, usernames or any other string
    * All strings in UiPath have to be placed in between quotes
2. Boolean
    * A type of variable that only has two possible values, true or false
    * These variables enable you to make decisions, and thus have a better control over your flow
3. Int32
    * Used to store numeric information
    * They can be used to perform equations or comparisons, pass important data and many others
4. Array []
    * The array variable is a type of variable which enables you to store multiple values of the same type
    * UiPath Studio supports as many types of arrays as it does types of variables
    * You can create an array of numbers, one of strings, one of boolean values and so on
5. Date and Time
    * The date and time variable is a type of variable that enables you to store information about any date and time
    * This type of variable can be found in the **Browse and Select a .Net Type** window, under the System namespace `System.DateTime`
6. Data Table
    * DataTable variables represent a type of variable that can store big pieces of information
    * Act as a database or a simple spreadsheet with rows and columns
    * They can be found in the **Browse and Select a .Net Type** window, under the System.Data namespace (System.Data.DataTable)
    * These variables can be useful to migrate specific data from a database to another, extract information from a website and store it locally in a spreadsheet and many others

##### Reference
[https://docs.uipath.com/studio/docs/types-of-variables](https://docs.uipath.com/studio/docs/types-of-variables)

#### Propietary Variables
1. GenericValue
    * A type of variable that can store any kind of data, including text, numbers, dates, and arrays, and is particular to UiPath Studio
    * Automatically converted to other types, in order to perform certain actions
2. QueueItem

##### Reference
[https://docs.uipath.com/studio/docs/uipath-proprietary-variables](https://docs.uipath.com/studio/docs/uipath-proprietary-variables)

---

> Describe the functions and differences between variables and arguments; including how arguments are used, managed, and best practices


#### Variables vs. Arguments
|Variables|Arguments|
|---------|---------|
|Used to pass data from one activity to another within a workflow|Used to pass data from a workflow to another|
|Don't have directions like In, Out, or In/Out|Do have directions like In, Out, In/Out|
|To create a variable press: `Ctrl + K`|To create an In Argument press: `Ctrl + M`<br/>To create an Out Argument press: `Ctrl + Shift + M`|
|To create variables, there must be at least one activity in the Designer Panel|Can be created if the Designer Panel doesn't contain any activity|
|Variables aren't used with the Invoke workflow file and Launch workflow Interactive activities|Used a lot in relation with the Invoke workflow file and Launch workflow Interactive activities|
|Require a defined scope|Do not require a scope|


#### Arguments
* Arguments are used to pass data from a project to another
* They resemble variables, as they store data dynamically and pass it on

#### Create Arguments
1. From the Body of an Activity
2. From Expressions
3. From Properties Panel
4. From Arguments Panel

#### Removing Arguments

##### Reference
[https://docs.uipath.com/studio/docs/managing-arguments](https://docs.uipath.com/studio/docs/managing-arguments)


### UiPath Studio ??? Classic Selectors

> Identify and describe how dynamic versus static selectors are used

#### Selectors
* Store the attributes of a graphical user interface element and its parents, in the shape of an XML fragment
* Most of the time, selectors are automatically generated by Studio and do not require further input from you, especially if the apps you are trying to automate have a static user interface

#### Dynamic Selectors
* Uses a variable or an argument as a property for the attribute of your target tag
* Allows the selector to easily identify a target element based on the value of the variable or argument, and not an exact string, which might change, depending on interactions inside your automation project
* The variable or argument can be changed to interact with a different element, without changing the selector itself

---

> Identify and describe how partial versus full selectors are used

#### Full Selectors
* Contains all the tags and attributes needed to identify a UI element, including top-level window
* Generated by the Basic recorder
* Recommended when switching between multiple windows

#### Partial Selectors
* Generated by the Desktop recorder
* Do not contain information about the top-level window
* Recommended when performing multiple actions in the same window

---

> Identify and describe how and when to use the Anchor Base activity


---

> Demonstrate and describe the use of a reliable selector and how to use UI Explorer to modify selectors

#### Recording
* Help you save a lot of time when automating your business processes
* This functionality enables you to easily capture a user???s actions on the screen and translates them into sequences

##### Reference
[https://docs.uipath.com/studio/docs/about-recording](https://docs.uipath.com/studio/docs/about-recording)

#### Recording Types
1. Basic
    * Generates a full selector for each activity and no container
    * The resulted automation is slower than one that uses containers and is suitable for single activities
2. Desktop
    * Suitable for all types of desktop apps and multiple actions
    * Faster than the `Basic` recorder, and generates a container (with the selector of the top-level window) in which activities are enclosed, and partial selectors for each activity
3. Web
    * Designed for recording in web apps and browsers, generates containers and uses the `Simulate Type/Click` input method by default
4. Image
    * Used to record virtualized environments or SAP
    * It permits only image, text and keyboard automation, and requires explicit positioning
5. Native Citrix
    * Is the equivalent of the `Desktop` recorder, but for Citrix environments
    * Only use this in your Native Citrix automation projects

[https://docs.uipath.com/studio/docs/about-recording-types](https://docs.uipath.com/studio/docs/about-recording-types)

### UiPath Studio ??? Control Flow

> Describe the functionality of the Control Flow activities (for example: If, Switch, While, Do While, For Each, etc.) and workflow types

> Explain how to use Control Flow activities and workflow types (sequences and flowcharts)

#### Control Flow
* The order in which activities are executed or evaluated in a software project
* A concept borrowed from computer science that refers to the order in which actions are performed in an automation
* A proper Control Flow can be achieved through the intelligent use of variables and activities
* All of these activities can be found in the `Activities` panel, under `Workflow` > `Control`

##### Reference
[https://docs.uipath.com/studio/docs/about-control-flow](https://docs.uipath.com/studio/docs/about-control-flow)

#### Control Flow Activities

1. The Assign Activity
    * It enables you to assign a value to a variable
    * You can use an Assign activity to increment the value of a variable in a loop
2. The Delay Activity
    * Enables you to pause the automation for a custom period of time (in the hh:mm:ss format)
    * Useful in projects that require good timing, such as waiting for a specific application to start 
3. The Do While Activity

4. The If Activity

5. The Switch Activity

6. The While Activity

7. The For Each Activity

8. The Break Activity

#### Types of Workflows
1. Sequences
2. Flowcharts
3. State Machines
4. Global Exception Handler




---

> Explain the importance of error handling and how it can be implemented

### UiPath Studio ??? Data Manipulation

> Describe the importance and reasons why data manipulation is used; for example, conversion from one data type to another data type

#### Data Manipulation
* The process of modifying, structuring, formatting, or sorting data in order to facilitate its usage and increase its management capabilities

---

> Explain how strings can be manipulated; for example, by using VB string methods and RegEx Builder

#### String Manipulation
* It is done by using String Methods borrowed from VB.Net. Below are some of the most common methods used in RPA
1. String.Concat
2. Contains
3. String.Format
4. IndexOf
5. LastIndexOf
6. String.Join
7. Replace
8. Split
9. Substring

#### RegEx Builder
* Also known as Regular Expression (REGEX, or regexp) is a specific search pattern that can be used to easily match, locate and manage text
* Typical uses of RegEx includes:
    * Input validation
    * String parsing
    * Data scraping
    * String manipulation

#### RegEx Builder Methods
1. Matches
2. IsMatch
3. Replace

##### Reference
[https://academy.uipath.com/courses/data-manipulation-with-strings-in-studio](https://academy.uipath.com/courses/data-manipulation-with-strings-in-studio)

---

>  Explain how to iterate and manipulate data on various collections; for example, lists, datatables, dictionaries

### UiPath Automation Concepts and Techniques

> Identify and explain how email automation is used


---

> Identify and describe Microsoft Excel functions and how Excel activities are used for spreadsheet manipulation

> Describe the functions used to extract data from a .pdf file; for example, reading native text or using OCR


### UiPath Orchestrator Overview

> Identify and describe how UiPath Orchestrator queues and assets are used

#### Queues
* Queues are containers that can hold an unlimited number of items
* Items can store multiple types of data, by default in free form
* If specific data schema is needed, it can be uploaded at queue creation in the form of a JSON file
* Queues in Orchestrator will store items and enable their distribution individually to robots for processing
* Queues also monitor the status of the items based on process outcomes


#### Creating a Queue
1. In the `Queues` page, click `Add Queue`
2. Click `Create a new queue`
3. In the `Name` field, enter a name for the queue
4. In the `Description` field, add a description for the queue
5. Select the `Enforce unique references` checkbox if you want transaction references to be unique or not (Optional)
6. Select the `Store in encrypted format` checkbox if you want to have queue items data and output encrypted in the database (Optional)
7. Select the `Auto Retry` checkbox if you want to use the auto-retry mechanism
    * In the `Max # of retries` field, input the number of times you want a queue item to be retried
8. Upload a JSON schema for any or each of `Specific Data`, `Output Data`, and `Analytics Data` by using the corresponding `Browse` button
9. Enable SLA predictions if you want to better control the processing time of your items, and to assess what resources you need such that they meet their deadline
    * If enabled, configure the following fields:
        1. From the `Process` drop-down, select the process which handles the queue items, and then fill in the SLA value below (maximum value is 90 days)
        2. Enable Risk SLA if you want to define a buffer zone before the actual SLA, and fill in the value below (risk SLA must be smaller than the SLA)
10. Click `Add`

#### Editing Queues
* You are able to update an existing queue settings such as:
    * The queue `Name` and `Description`
    * The `Auto Retry` option
    * The maximum number of retries

##### For Name or Description
1. In the `Queues` page, click the `More Options` button for the desired queue
2. Click `Edit`, then the `Update Queue` wizard is displayed
3. In the `Name` field, enter the new name for the selected queue
4. In the `Description` field, update the description of your queue
5. Click `Update`

##### For Auto Retry
1. In the `Queues` page, click the `More Options` button for the desired queue
2. Click `Edit`, then the `Update Queue` wizard is displayed
3. In the `Auto Retry` field, select the option you need
4. Click `Update`

##### Reference
[https://docs.uipath.com/orchestrator/docs/managing-queues-in-orchestrator](https://docs.uipath.com/orchestrator/docs/managing-queues-in-orchestrator)

#### Populating & Consuming Queues
* Queues are typically used with the Dispatcher-Performer model of running automation
* The Dispatcher is the stage in which data is taken and fed into a queue in Orchestrator, from where it can be taken and processed by robots
* The Performer is the stage in which data is processed

#### Assets
* Assets usually represent shared variables or credentials that can be used in different automation projects
* They allow you to store specific information so that the Robots can easily access it

#### Types of Assets
1. Text         : Stores only strings (it is not required to add quotation marks)
2. Bool         : Supports true or false values
3. Integer      : Stores only whole numbers
4. Credential   : Contains usernames and passwords that the Robot requires to execute particular processes, such as login details for SAP or SalesForce

#### Managing Assets

##### Through Studio Using the Get Asset Activity
1. In Orchestrator, create a string, boolean or integer asset
2. In Studio, create a string, boolean or integer variable, depending on the type of asset you want to use from Orchestrator
3. From the `Activities` panel, drag a `Get Asset` activity to the `Main` panel
4. In the `Properties` panel, in the `AssetName` field, type the name of the Orchestrator asset you want to use, and place it between quotation marks
5. In the `Properties` panel, in the `Value` field, enter the variable created at step 2
    * This variable stores information from the specified Orchestrator asset, if the `AssetName` coincides with the asset name that is stored in the Orchestrator database, and the Robot has the required permissions

##### Through Studio Using the Get Credential Activity
1. In Orchestrator, create a `Credential` asset
2. In Studio, create a String variable which is used to store the username part of the credentials
3. Create a SecureString variable to store the password
4. In the `Properties` panel, in the `AssetName` field, type the name of the credential asset, as it is in Orchestrator, and place it between quotation marks
5. In the `Properties` panel, in the `Password` field, enter the SecureString variable
6. In the `Properties` panel, in the `Username` field, enter the string variable
    * The credential asset stored in Orchestrator can be used by the Robot too, as long as the AssetName coincides with the asset name that is stored in the Orchestrator database, and the Robot has the required permissions

---

> Identify and explain how to publish projects to UiPath Orchestrator

1. In Studio, create a new project
2. In the `Design` ribbon tab, click `Publish`
3. In the `Package` properties tab:
    * Enter a name for the package
    * In the `Version` section, review the Current Version of your project, and type a New Version if needed
    * In the `Project` tags box, you can add one or more tags to the project, either by creating new ones or by reusing tagsalready defined in Orchestrator
    * In the `Release Notes` text box, enter details about the version and other relevant information
4. Click `Next`
5. In the `Publish` options tab, select where to publish the project. The available options depend on the type of project you are publishing:
    * For processes:
        * Orchestrator Tenant Process Feed
        * Assistant
        * Custom
    * For test cases:
        * The same options available for processes
    * For libraries and UI libraries:
        * Local
        * Custom
    * For templates:
        * Local
        * Custom
