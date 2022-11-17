---
title: "Integrated Software Development Environments"
start: false
teaching: 25
exercises: 15
questions:
- "What are Integrated Development Environments (IDEs)?"
- "What are the advantages of using IDEs for software development?"
objectives:
- "Set up a (virtual) development environment in VS Code"
- "Use VS Code to run a Python script"

keypoints:
- "An IDE is an application that provides a comprehensive set of facilities for software development, including
syntax highlighting, code search and completion, version control, testing and debugging."
- "With the correct extensions installed VS Code recognises virtual environments configured from the command line using `venv` and `pip`."
---

## Introduction
As we have seen in the
previous episode - even a simple software project is typically split into smaller functional units and modules which are kept in separate files and subdirectories.
As your code starts to grow and becomes more complex, it will involve many different files and various external libraries. You will need an application to help you manage all the complexities of, and provide you with some useful (visual)
facilities for, the software development process. Such clever and useful graphical
software development applications are called Integrated Development Environments (IDEs).

## Integrated Development Environments (IDEs)
An IDE normally consists of at least a source code editor, build automation tools and a debugger.
The boundaries between modern IDEs and other aspects of the broader software development process are often blurred as
nowadays IDEs also offer version control support, tools to construct graphical user interfaces (GUI) and web browser
integration for web app development, source code inspection for dependencies and many other useful functionalities. The
following is a list of the most commonly seen IDE features:

- syntax highlighting - to show the language constructs, keywords and the syntax errors with visually distinct colours
and font effects
- code completion - to speed up programming by offering a set of possible (syntactically correct) code options
- code search - finding package, class, function and variable declarations, their usages and referencing
- version control support - to interact with source code repositories
- debugging - for setting breakpoints in the code editor, step-by-step execution of code and inspection of variables

IDEs are extremely useful and modern software development would be very hard without them. There are a number of IDEs
available for Python development; a good overview is available from the
[Python Project Wiki](https://wiki.python.org/moin/IntegratedDevelopmentEnvironments). In addition to IDEs,
there are also a number of code editors that have
Python support. Code editors can be as simple as a text editor with syntax highlighting and code formatting capabilities
(e.g. GNU EMACS, Vi/Vim, Atom). Most good code editors can also execute code and control a
debugger, and some can also interact with a version control system. Compared to an IDE, a good dedicated code
editor is usually smaller and quicker, but often less feature-rich. You will have to decide which one is the best for
you - in this course we will learn how to use [VS Code](https://code.visualstudio.com/), a free code editor from Microsoft. Some popular alternatives include free and open source IDE [Spyder](https://www.spyder-ide.org/) and [PyCharm](https://www.jetbrains.com/pycharm/), a free open source Python IDE.

## Using Visual Source Code

Let's open our project in VS Code now and familiarise ourselves with some commonly used features.

### Opening a Software Project
If you don't have VS Code running yet, start it up now. If this is the very first time that you are running VS Code you should be presented with a windows such as in the image below.

![Startup screen of VS Code](../fig/vsc/00_vsc_getstarted_theme.png)

On this screen you can select the theme that you would like. There are two light themes, i.e. dark text on a light background and two dark themes, i.e. light text on a dark background. Select the theme that you think would give you the best environment to work in. When you have made your selection, click on `Next Section` at the bottom of the screen.

At this point, we can ignore the next screen which allows you to configure your editing environment. Just click `Next Section` at the bottom of the screen.

![Editor Playground](../fig/vsc/01_vsc_getstarted_editor.png)

On the next screen you would want to select `Side by side editing` and `Install Git`. Leave `Customize your shortcuts` unticked for now. When done, click `Mark Done`.

![Split screen](../fig/vsc/02_vsc_getstarted_splitscreen.png)

Select `Open Folder` to find the software project directory `python-intermediate-inflammation` you cloned earlier. 

![Open Folder](../fig/vsc/03_vsc_getstarted_open.png )

A window will pop up asking whether you trust the authors of the files in the folder. You can click the button that says: "Yes, I trust the authors. Trus folder and enable all features." You could also tick the box above to "Trust the authors of all files in the parent folder".

![Trust](../fig/vsc/04_vsc_getstarted_trust.png)

This directory is now the current working directory for VS Code, so when we run scripts from VS Code,
this is the directory they will run from.

You will notice the editor showing you a list of icons on the left hand side, just below the VS Code logo. This area is called the `Activity Bar`. From top to bottom these are:
- Explorer
- Search
- Source Control
- Run and Debug
- Extensions

If you hover over these icons with your mouse a tooltip should pop up showing you what each icon is for. You should also now see the file explorer opened on the left hand side, the `Side Bar`, showing you a tree view of the files in the selected folder. The explorer icon will also be highlighted, while the others are greyed:

![Get started explorer](../fig/vsc/05_vsc_getstarted_explorer.png)

Select the `inflammation-analysis.py` file in the 'Side Bar'. The file will open in the editor window, but at the bottom of the screen you will see a notification with the question, `Do you want to install the recommended extentions for Python?` Click the `Install` button.

![Get Python extensions](../fig/vsc/06_vsc_open_inflammation.png)

On the next window you will be able to install the Python extension. Click the install button.

![Install Python extension](../fig/vsc/07_vsc_python_extension.png)

After the installation more tabs might have opened next to the inflammation-analysis.py tab. You can close those tabs by clicking on the X in the tab next to the tab name, but leave the inflammation-analysis.py tab obpen. You might also have noticed in the `Side Bar` the `Explorer` has been replaced by `Extensions` and the extension icon in the `Activity Bar` is now hightlighted, while the others are greyed. 

![Extension installed](../fig/vsc/09_vsc_extension_installed.png)

### Configuring the Terminal
VS Code has a built-in terminal which you can open, as sometimes you might want to execute commands directly in the terminal. By default VS Code, in Windows, will open the PowerShell which has restricted access. You can see what this looks like by clicking `Terminal` on the menu and then selecting `New Terminal`. The new terminal should open at the bottom of the screen. If you still have the `inflammation-analysis.py` file open, you might see error message displayed as in the screenshot below:

![Error in terminal](../fig/vsc/10_terminal_error.png)

To change the default terminal, look at the top of the terminal section. There should be a `> powershell` button. Click on the `v` arrow to the right of the `> powershell` button and select `Git Bash`.

![Select Git Bash shell](../fig/vsc/11_select_GitBash.png)

A `Git Bash` shell should have opened. You should see (.venv) displayed in the shell which means the virtual environment has been detected. There should be no error messages. To the right hand side of the terminal you should notice a section displaying two shells - the powershell that we had open before and below that `bash` which is our current `Git Bash` shell. 

![Git Bash](../fig/vsc/12_gitbash.png)

You can close the powershell by hovering over the button with the mouse at which time a garbage bin should appear next to it. Click on the garbage bin to close the terminal. The `bash` shell should remain open.

![Close Powershell](../fig/vsc/13_close_powershhell.png)

### Configuring a Virtual Environment in VS Code
Because we created the `venv` environment before we opened the project in VS Code, VS Code and the Python extension were able to detect the environment. We could see that this was the case when we opened the terminal and saw `(.venv)` displayed before the prompt.

If we didn't create the virtual environment beforehand we can do after we opened the project folder in VS Code. To create such a virtual environment you have to click `Ctrl+Shift+P`. In the search box, start typing 'Python: Create Environment'. You won't have to completely type the string before you'll notice it in the list. Click on `Python: Create Environment`. Then select `Venv Creates a '.venv' virtual environment in the the current workspace`.

You should now get a list of installed Python interpreters. You should select the one that is required for your project. A `.venv` directory will now be created. You should be able to se this happen in the explorer tab.


#### Adding an External Library
We have already added packages `numpy` and `matplotlib` to our virtual environment from the command line
in the previous episode, so we are up-to-date with all external libraries we require at the moment. However, we will need library `pytest` soon to implement tests for our code so will use this 
opportunity to install it from VS Code. Strictly speaking VS Code is not an IDE but a code editor which is why we still need to do things in the terminal. An IDE such as PyCharm will have alternative ways to do this via the Graphic User Interface.

1. If you already have an open terminal at the bottom of the screen you can enter the following commands in there. If you don't have a terminal open you can open one by clicking on the `Terminal` menu item and then selecting `New Terminal`.
2. Double check that your virtual environment is active by looking for `(.venv)` displayed with your prompt.
3. As before we will use pip3 to install the library. In the terminal type: `pip3 install pytest`. It might take a few minutes to install.

Pytest should now be installed. You can also verify this from the command line by listing the `venv/lib/python3.9/site-packages` subdirectory. Note, however, that `requirements.txt` is not updated - as we mentioned earlier this is something you have to do manually. Let's do this as an exercise.

>## Exercise: Update `requirements.txt` After Adding a New Dependency
Export the newly updated virtual environment into `requirements.txt` file.
>>## Solution
>>Let's verify first that the newly installed library `pytest` is appearing in our virtual environment
>>but not in `requirements.txt`. First, let's check the list of installed packages:
>> ~~~
>> (venv) $ pip3 list
>> ~~~
>> {: .language-bash}
>> ~~~
Package         Version
--------------- -------
attrs           21.4.0 
cycler          0.11.0 
fonttools       4.28.5 
iniconfig       1.1.1  
kiwisolver      1.3.2  
matplotlib      3.5.1  
numpy           1.22.0 
packaging       21.3   
Pillow          9.0.0  
pip             20.0.2 
pluggy          1.0.0  
py              1.11.0 
pyparsing       3.0.7  
pytest          6.2.5  
python-dateutil 2.8.2  
setuptools      44.0.0 
six             1.16.0 
toml            0.10.2 
tomli           2.0.0  
>> ~~~
>> {: .output}
>> We can see the `pytest` library appearing in the listing above. However, if we do:
>>~~~
>>(venv) $ cat requirements.txt
>>~~~
>>{: .language-bash}
>>~~~
cycler==0.11.0
fonttools==4.28.1
kiwisolver==1.3.2
matplotlib==3.5.0
numpy==1.21.4
packaging==21.2
Pillow==8.4.0
pyparsing==2.4.7
python-dateutil==2.8.2
setuptools-scm==6.3.2
six==1.16.0
tomli==1.2.2
>>~~~
>>{: .output}
>> `pytest` is missing from `requirements.txt`. To add it, we need to update the file by repeating the command:
>>~~~
>>(venv) $ pip3 freeze > requirements.txt
>>~~~
>>{: .language-bash}   
>> `pytest` is now present in `requirements.txt`:
>>~~~
attrs==21.2.0
cycler==0.11.0
fonttools==4.28.1
iniconfig==1.1.1
kiwisolver==1.3.2
matplotlib==3.5.0
numpy==1.21.4
packaging==21.2
Pillow==8.4.0
pluggy==1.0.0
py==1.11.0
pyparsing==2.4.7
pytest==6.2.5
python-dateutil==2.8.2
setuptools-scm==6.3.2
six==1.16.0
toml==0.10.2
tomli==1.2.2
>>~~~
>{: .solution}
{: .challenge}

#### Adding a Run Configuration for Our Project
Having configured a virtual environment, we now need to tell PyCharm to use it for our project. This is done by adding a **Run Configuration** to a project:

1. To add a new configuration for a project - select `Run` > `Edit Configurations...` from the top menu.
2. Select `Add new run configuration...` then `Python`.
   ![Adding a Run Configuration in PyCharm](../fig/pycharm-add-run-configuration.png){: .image-with-shadow width="800px" }
3. In the new popup window, in the `Script path` field select the folder
   button and find and select `inflammation-analysis.py`. This tells PyCharm which script to run (i.e. what the main entry point to our application is).
   ![Run Configuration Popup in PyCharm](../fig/pycharm-run-configuration-popup.png){: .image-with-shadow width="800px" }
4. In the same window, select "Python 3.9 (python-intermediate-inflammation)" (i.e. the virtual environment and interpreter you configured earlier in this episode) in the `Python interpreter` field.
5. You can give this run configuration a name at the top of the window if you like - e.g. let's name it `inflammation analysis`.
6. You can optionally configure run parameters and environment variables in the same window - we do not need this at the moment.
7. Select `Apply` to confirm these settings.

> ## Virtual Environments & Run Configurations in PyCharm
>
> We configured the Python interpreter to use for our project by pointing PyCharm to the
> virtual environment we created from the command line (which also includes external libraries
> our code needs to run).
> Recall that you can create several virtual environments based on the same Python interpreter but with
different external libraries - this is helpful when you need to develop different types of applications.
> For example, you can create one virtual environment based on Python 3.9 to develop Django Web applications and another virtual environment based on the same Python 3.9 to work with scientific libraries.
>
> **Run Configurations** in PyCharm are named sets of startup properties that define what to execute and what parameters (i.e. what additional configuration options) to use on top of virtual environments.
> You can vary these configurations each time your code is executed, which is particularly useful for running, debugging and testing your code.
{: .callout}

Now you know how to configure and manipulate your environment in both tools (command line and PyCharm), 
which is a useful parallel to be aware of. Let's have a look at some other features afforded to us by 
PyCharm.

### Syntax Highlighting
The first thing you may notice is that code is displayed using different colours.
Syntax highlighting is a feature that displays source code terms in different colours and fonts according to the syntax
category the highlighted term belongs to. It also makes syntax errors visually distinct. Highlighting does not affect
the meaning of the code itself - it's intended only for humans to make reading code and finding errors easier.

![Syntax Highlighting Functionality in PyCharm](../fig/pycharm-syntax-highlighting.png){: .image-with-shadow width="1000px" }

### Code Completion
As you start typing code, PyCharm will offer to complete some of the code for you in the form of an auto completion popup.
This is a context-aware code completion feature that speeds up the process of coding (e.g. reducing typos and other
common mistakes) by offering available variable
names, functions from available packages, parameters of functions, hints related to syntax errors, etc.

![Code Completion Functionality in PyCharm](../fig/pycharm-code-completion.png){: .image-with-shadow width="600px" }

### Code Definition & Documentation References
You will often need code reference information to help you code. PyCharm shows this useful information, such as definitions of symbols (e.g. functions, parameters, classes, fields, and methods) and documentation references by means of quick popups and inline tooltips.

For a selected piece of code, you can access various code reference information from the `View` menu (or via various keyboard shortcuts), including:
- Quick Definition - where and how symbols (functions, parameters, classes, fields, and methods) are defined
- Quick Type Definition - type definition of variables, fields or any other symbols
- Quick Documentation - inline documentation (*docstrings*) for any symbol created in accordance with [PEP-257](../05-coding-conventions/index.html#documentation-strings-aka-docstrings))
- Parameter Info - the names of parameters in method and function calls
- Type Info - type of an expression

![Code References Functionality in PyCharm](../fig/pycharm-code-reference.png){: .image-with-shadow width="1000px" }

### Code Search
You can search for a text string within a project, use different scopes to narrow your search process, use regular expressions
for complex searches, include/exclude certain files from your search, find usages and occurrences. To find a search string
in the whole project:

1. From the main menu, select `Edit | Find | Find in Path ...` (or `Edit | Find | Find in Files...` depending on your version of PyCharm).
2. Type your search string in the search field of the popup. Alternatively, in the editor, highlight the string you
want to find and press `Command-Shift-F` (on Mac) or `Control-Shift-F` (on Windows). PyCharm places the highlighted
string into the search field of the popup.

    ![Code Search Functionality in PyCharm](../fig/pycharm-code-search.png){: .image-with-shadow width="800px" } 
    If you need, specify the additional options in the popup. PyCharm will list the search strings and all the files that contain them.
3. Check the results in the preview area of the dialog where you can replace the search string or select another string,
or press `Command-Shift-F` (on Mac) or `Control-Shift-F` (on Windows) again to start a new search.
4. To see the list of occurrences in a separate panel, click the `Open in Find Window` button in the bottom right
corner. The find panel will appear at the bottom of the main window; use this panel and its options to group the results, preview them, and work with them further.

    ![Code Search Functionality in PyCharm](../fig/pycharm-find-panel.png){: .image-with-shadow width="1000px" }

### Version Control
PyCharm supports a directory-based versioning model, which means that each project directory can be
associated with a different version control system. Our project was already under Git version control and PyCharm
recognised it. It is also possible to add an unversioned project directory to version control directly from PyCharm.

During this course, we will do all our version control commands from the command line but it is worth
noting that PyCharm supports a comprehensive subset of Git commands (i.e. it is possible to perform a set of common
Git commands from PyCharm but not all). A very useful version control feature in PyCharm is graphically comparing
changes you made locally to a file with the version of the file in a repository, 
a different commit version or a version in a different
branch - this is something that cannot be done equally well from the text-based command line.

You can get a full
[documentation on PyCharm's built-in version control support](https://www.jetbrains.com/help/pycharm/version-control-integration.html) online.

![Version Control Functionality in PyCharm](../fig/pycharm-version-control.png){: .image-with-shadow width="1000px" }

### Running Scripts in PyCharm
We have configured our environment and explored some of the most commonly used PyCharm features and are now ready to run our script from PyCharm! To do so, right-click the `inflammation-analysis.py` file in the PyCharm project/file navigator on the left, and select `Run 'inflammation analysis'` (i.e. the Run Configuration we created earlier).

![Running a script from PyCharm](../fig/pycharm-run-script.png){: .image-with-shadow width="800px" }

The script will run in a terminal window at the bottom of the IDE window and display something like:

~~~
/Users/alex/work/python-intermediate-inflammation/venv/bin/python /Users/alex/work/python-intermediate-inflammation/inflammation-analysis.py
usage: inflammation-analysis.py [-h] infiles [infiles ...]
inflammation-analysis.py: error: the following arguments are required: infiles

Process finished with exit code 2
~~~
{: .output}

This is the same error we got when running the script from the command line. We will get back to this error
shortly - for now, the good thing is that we managed to set up our project for development both from the
command line and PyCharm and are getting the same outputs.
Before we move on to fixing errors and writing more code, let's have a look at the last set of tools for collaborative
code development which we will be using in this course - Git and GitHub.

{% include links.md %}




