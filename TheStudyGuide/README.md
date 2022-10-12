# Study Guide Here
Everything is in the UiPath exam documentation on the UiPath website. It's just that finding the answers is hard and hope the answers found aligns with what you're going to get with on the exam. And hands-on training.

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

> Explain the functionality and interactions of UiPath products; Studio, Orchestrator, and Assistant

**The BIG three**
1. UiPath Studio
2. UiPath Orchestrator
3. UiPath Robots

#### UiPath Studio Interface

**The Designer Panel**
* Used to design automation projects by dragging and dropping activities into it.

**The Project Panel**
* Displayed as a tree structure, where the root node is the name of the project and the branches contain the dependencies, inputs, settings and project files

**The Activities Panel**
* Helps you select the right activity to be added to your automation.

**The Properties Panel**
* To manage the properties of various activities and to manage variables.

**The Variables Panel**
* Enables you to create variables and make changes to them

**The Arguments Panel**
* Used when accessing a workflow to pass input through an argument or get the output from an argument or input/output from an argument.

**The Output Panel**
* To verify the results of the workflow using log messages or writing line activities

**The Outline Panel**
* Used to view the hierarchy of the selected workflow and all nodes available inside the workflow

#### UiPath Orchestrator
* Manages all the published automation solutions developed in Studio
* Execute of tasks by robots
* Execution schedules

**Capabilities**
* Provisioning
* Deployment
* Configuration
* Monitoring
* Queues
* Integrated Connectivity
* Version Control

#### Robots
* Are known as execution agents, execute the workflows created in UiPath Studio.

**Robot Types**
* Standard
* Floating

1. Attended
2. Unattended
3. Development
4. Non-Production

### UiPath Studio Overview
> Explain the debug functions and how they are used

#### What is Debugging?

The process of identifying and resolving errors that prevent the project from functioning correctly. It is recommended to perform debugging during the design stage of the automation project, at activity, file and project level. By default, debugging is performed on the local robot.

#### Start Debugging

The options for running and debugging a file or project are available in the Design and Debug tabs.

* Debug         :   Click Debug or use `F5` to debug the whole project.
* Run           :   Click Run or use `Ctrl + F5` to run the whole project.
* Debug File    :   Click Debug File or use `F6` to debug the current file.
* Run File      :   Click Run File or use `Ctrl + F6` to run the file.
* Stop          :   Click the Stop or use `F12` to exit debug mode and return to design mode.

Note that the default action of the Play button in the Ribbon is Debug Current File.

#### The 'Hands-On' in the Debugging Panel

The debugging actions located on both the Design or Debug ribbon tabs. However, the debugging process is not available if project files have validation errors

* Step Into
    * To debug activities one at a time. When triggered, the debugger opens and highlights the activity before it is executed
    * When used with Invoke Workflow File activities, the workflow is opened in a new tab in `ReadOnly` mode and each activity is executed one by one
    * The keyboard shortcut for Step Into is `F11`
* Step Over
    * Does not open the current container. When used, the action debugs the next activity, highlighting containers without opening them
    * Comes in handy for skipping analysis of large containers which are unlikely to trigger any issues during execution
    * The keyboard shortcut for Step Over is `F10`
* Step Out
    * This action is used for stepping out and pausing the execution at the level of the current container. It completes the execution of activities in the current container, before pausing the debugging
    * This option works well with nested sequences
    * The keyboard shortcut for Step Out is `Shift + F11`
* Retry
    * Re-executes the previous activity, and throws the exception if it's encountered again. The exception is highlighted and details about the error are shown in the `Locals` and `Call Stack` panels
* Ignore
    * Ignore an encountered exception and continue the execution from the next activity so that the rest of the workflow can be debugged.
* Restart
    * Available after the exception was thrown and the debug process is paused
    * The action is used for restarting the debugging process from the first activity of the project
* Break
    * Allows you to pause the debugging process at any given amount. The activity which is being debugged remains highlighted when paused. Once this happens, you can choose to Continue, Step Into, Step Over, or Stop the process
    * Recommended to use Break along with Slow Step so that you know exactly when the debugging needs to be paused
* Focus
    * Helps return to the current breakpoint or the activity that caused an error during debugging
* Slow Step
    * Enables to take a closer look at any activity during debugging
    * Can be activated both before or during the debugging process. Activating the action does not pause debugging
    * Comes with 4 different speeds tha range from 1X to 4X with 1X being the slowest
* Execution Trail
* Highlight Elements
* Log Activities
* Continue on Exception
* Picture in Picture
* Remote Debugging
* Open Logs


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

**Version Control Available**
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


### UiPath Studio – Variables and Arguments

> Describe the different variables' types, how they are used, managed, and the best practice for using the variable scope

> Describe the functions and differences between variables and arguments; including how arguments are used, managed, and best practices

### UiPath Studio – Classic Selectors

> Identify and describe how dynamic versus static selectors are used

> Identify and describe how partial versus full selectors are used

> Identify and describe how and when to use the Anchor Base activity

> Demonstrate and describe the use of a reliable selector and how to use UI Explorer to modify selectors

### UiPath Studio – Control Flow

### UiPath Studio – Control Flow
