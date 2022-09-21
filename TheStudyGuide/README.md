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

#### The 'Hands-On Stuff You Need To Do' in the Debugging Panel

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
* Rety
* Ignore
* Restart
* Break
* Focus
* Slow Step
* Execution Trail
* Highlight Elements
* Log Activities
* Continue on Exception
* Picture in Picture
* Remote Debugging
* Open Logs


> Identify how to manage dependencies

> Understand the significance of connecting an automation project to a version control solution

## UiPath Studio – Variables and Arguments

> Describe the different variables' types, how they are used, managed, and the best practice for using the variable scope

> Describe the functions and differences between variables and arguments; including how arguments are used, managed, and best practices

## UiPath Studio – Classic Selectors

> Identify and describe
