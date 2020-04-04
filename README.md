# HWRS 482/582 Applied Groundwater Modeling

This repo contains course materials for HWRS 482/582

____
## Table of Contents:
1. [ Zoom Info](#zoom)
1. [ Announcements](#announcements)
1. [ Homework](#homeworks)
1. [ Discussion Leaders](#discuss)
2. [ Repo Contents](#repo-contents)
3. [ Helpful Links and Tutorials](#tutorials)
4. [ Getting Started - Software install instructions](#softwareinstall)
   - [ Python](#python)
   - [ GitHub](#python)
   - [ Course Repo](#repo)
   - [ MODFLOW](#modflow)
   - [ Jupyter PDF](#jupyterpdf)
5. [ Software Install Debugging tips](#debug)
6. [ Getting Started - Homework and GitHub Classroom](#github)
7. [Optional additional software to install](#additionalsoftware)
____
<a name="zoom"></a>
## Zoom Meeting Information

#### Class (Tuesday/Thursday, 12:30-1:45)
- Zoom meeting ID: 475 073 103
- Link: https://arizona.zoom.us/j/475073103

#### Monday Office Hours (Monday 1:30 - 2:30)
- Zoom Meeting ID: 955 245 726
- Link: https://arizona.zoom.us/j/955245726

#### Thursday Office Hours  (Thursday 10:00 - 11:00)
- Zoom Meeting ID: 792 507 016
- Link: https://arizona.zoom.us/j/792507016 Â
#### Final project groups:
 - Group 1: Amanda, Justin, Tesfa, Vivek
 - Group 2: Ben, Danielle, Jake
 - Group 3: Abe, Rachel, Dave

____
<a name="announcements"></a>
## Announcements:
**April 3**
- Homework 8 is posted and I have assigned the final project teams above.
Each group is responsible for one part of the assignment. You will just submit a powerpoint and one jupyter notebook for your group and you don't have to write individual submissions next week.

**March 19**
- Homework 6 is described in the Lectures/Python_Tutorials folder.  I wrote everyones names by the data type they are assigned to.  Please submit 1 ipython notebook to me by 12:00 on Tuesday and be prepared to present.

**March 13**
- Correction to HW5 question 2. Here is the correct wording:
  2. Go back to the original 0 ET rate for the steady state initialization of the model. This time run the transient  model for for more years to achieve an alternate steady state solution. How does this solution compare to the solution you determined in question 1. How did you determine that you are at steady state? (Hint it would be a good idea to decrease your outputs from daily to once every 5 days by adjusting the nstp variable).

**Feb 27**
- Homework 2 grades are now posted in your submission repos. Homework 4 will be posted this weekend and due next Thursday.

**Feb 25**
- Office hours this week are moved. I will have office hours on Wednesday the 26th from 10-11 and not on Thursday.

**Feb 18**
- I am traveling and there will be no office hours on the 24th.

**Feb 11**
- Reminder that there is no class this Thursday February 13th and also no office hours.

**Jan 30**
- Homework 0 is due today by the start of class. It will be graded for completion only.
- I have office hours today from 10-11 Harshbarger 324e_
- Homework 1 is due next Thursday February 6th. This is the link to clone:  https://classroom.github.com/a/AkI4KJaD
____
<a name="homeworks"></a>
## Homework assignments:
- Homework 8 (*Due Thursday April 8*) https://classroom.github.com/a/aNMCj9JD
- Homework 7 (*Due Thursday April 2*) https://classroom.github.com/a/OmX-bn_S
- Homework 6 (*Due Tuesday March 24*) No repo to clone. Create your own notebook as a group and email to me by 12:00.
- Homework 5 (*Due Thursday March 19*) https://classroom.github.com/a/cwN2GlJF
- Homework 4 (*Due Thursday March 5*) https://classroom.github.com/a/B0Up8OcI
- Homework 3 (*Due Thursday February 27*) https://classroom.github.com/a/bf6ehAbc
- Homework 2 (*Due Tuesday February 18*)  https://classroom.github.com/a/vqgQiD4l
- Homework 1 (*Due Thursday February 6*)  https://classroom.github.com/a/AkI4KJaD
____
<a name="discusss"></a>
## Discussion Leaders:
 - Feb. 18: Justin & Rachel  
 - Feb. 25: Dave and Danielle
 - Mar. 5: Amanda and Ben
 - Mar. 19: Abe and Tesfa
 - Apr. 2: Vivek and Jake
____
<a name="repo-contents"></a>
## Repo Contents
- **Lectures** - Notes and slides from lectures will be posted as they are completed.
- **Homework_Keys** - Keys for graded homework assignments will be available in this directory after they are submitted.
- **References** - General Reference materials.
____
<a name="tutorials"></a>
## Helpful Links and Tutorials
- **Flopy** <https://modflowpy.github.io/flopydoc/>
- **MODFLOW** <https://water.usgs.gov/ogw/modflow/MODFLOW-2005-Guide/>
- **Shell** <https://seankross.com/the-unix-workbench/command-line-basics.html#summary>
- **Jupyter**  <https://www.dataquest.io/blog/jupyter-notebook-tutorial/>
- **Markdown** <https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet>
____

<a name="softwareinstall"></a>
## Getting Started - Software install instructions
For this class we will use the following software packages.  Please follow the following instructions to get this setup on your laptop.

<a name="python"></a>
1.	**Install Python3 and Modules:** You can download this [here](https://www.python.org/downloads/). Make sure you pick the version that is right for your operating system.
 **MAKE SURE** when you do the install that you check the box to add it to your PATH.

    **Install Python Packages:** After you have installed python you will need the following packages. First open a terminal window (terminal for mac or Command Prompt for windows).

    To install you should run the following command from your terminal window **NOT** from within Python
      - Mac users:  
        `pip3 install modulename`
      - Windows users:  
        `python -m pip install modulename`

        Where *modulename* is the name of the module from the list below:
        - jupyter
        - numpy
        - requests
        - flopy
        - matplotlib
        - Pandas

      To check if you have installed these modules you can use the command `pip3 list`.

      Alternatively if you prefer you can install module using [Andaconda](https://www.anaconda.com/distribution/)

<a name="github"></a>
2.	**Setup account and install Github**
  - Register for account on GitHub: <https://github.com/>
  - Check if you have GitHub installed and if not install it.  Directions for both Windows & Mac [here](http://happygitwithr.com/install-git.html). Windows users should follow Option 1 in 6.2. Mac users can follow Option 1 in 6.3 if comfortable, otherwise follow Option 2. If you are a windows user make sure you also install [GitBash](https://www.atlassian.com/git/tutorials/git-bash) as is noted in the instructions.
  - Setup options in Git. In you have a Mac, you can go to the terminal if you have a Mac (Applications -> Utilities -> Terminal) as shown above. If you have a Windows, open Git BASH, which you should have downloaded in step 3.  You will need to  setup you [username](https://help.github.com/en/github/using-git/setting-your-username-in-git) and your [email](https://help.github.com/en/github/setting-up-and-managing-your-github-user-account/setting-your-commit-email-address)
  - Generate a SSH key so you don’t need to enter your password every time you interact with GitHub. Instructions for this can be found [here](https://help.github.com/en/github/authenticating-to-github/adding-a-new-ssh-key-to-your-github-account).  
  - Optional but recommended: Install [GitHub Desktop](https://desktop.github.com/) to manage your GitHub repos. This way you won't need to use command line for committing and pushing changes.

<a name="reop"></a>
3.	**Setup a directory for this class and clone main repo**
**GitHub Desktop Approach**
  - Go to the [Course Materials  Repo](https://github.com/groundwater-modeling-Spring2020/Course_Materials) and click on the green 'Clone or Download Button'
  - When you do this you should see an 'Open in Desktop' option  this will create a clone and open it into desktop directly for you.

**Command Line Approach**
  - Make a directory for this class wherever you would like to have it on your computer
  - Open a terminal window and navigate to your course directory (you can do this using the commands cd and pwd)
  - Clone the main course materials repo: `git clone git@github.com:groundwater-modeling-Spring2020/Course_Materials.git`
  (if your ssh keys aren't setup you can also clone it like this `git clone https://github.com/groundwater-modeling-Spring2020/Course_Materials`)  

<a name="modflow"></a>
4.	**Install MODFLOW**  
  **Mac Users:**  
    Run the following commands to install MODFLOW using the PyMake
  - Check if you have gfortran installed bu typing `which gfortran` or `gfortran -v` into command line. If you don't see that you have gfortran installed you should install it from [here](https://github.com/fxcoudert/gfortran-for-macOS/releases)
  - `cd` to a directory where you would like to put your MODFLOW builds
  - `Pip3 install https://github.com/modflowpy/pymake/zipball/master`
  - `git clone https://github.com/modflowpy/pymake`
  - `cd pymake/examples`
  - `python3 make_mf2005.py`
  - `python3 make_mp7.py`
  - The mp7 and mf2005 folders created in this step have the mode executables that you will need to point to when you are running MODFLOW. If you want to move these somewhere else you can do so now.

  **PC Users:**  
    - Follow [these install instructions](https://water.usgs.gov/ogw/modflow-nwt/MODFLOW-NWT-Guide/index.html?beginners_guide_to_modflow.htm)
    - You can download MODFLOW 2005 [here](https://www.usgs.gov/software/modflow-2005-usgs-three-dimensional-finite-difference-ground-water-model).

<a name="jupyterpdf"></a>
5. **Optional Jupyter Notbook PDF setup**
if you want to be able to convert to pdf from  within a Jupyter notebook you will need to do the following extra steps
   - Install [pandoc](https://pandoc.org/installing.html)
   - Install the nbconvert python module `pip install nbconvert`
   - Install XeTex for xelatex
      - Linux : [TeX Live](http://tug.org/texlive/)
      - Mac : [MacTex](http://tug.org/mactex/)
      - Windows : [MikTex](https://miktex.org/)
    - Once you have done this you can cover to pdf by typing the following from command line in the folder where your notbook sits: `jupyter nbconvert --to pdf MyNotebook.ipynb`
    - **NOTE** See the debug tip below if it is still not working you may need to export your LaTex path


____
<a name="debug"></a>
## Software Install Debugging tips
This is a running list of common issues and fixes if you run into issues please report them so we can add to this LIST

### Jupyter Notebooks:
- Issue with python code blocks not running: It turns out the kernels were not starting. Turns out ipykernel needed to be updated (now 5.1.4) for the new Notebook version (6.03) which was updated to work with Python (3.8).The latest ipykernel can be cloned from here - https://github.com/ipython/ipykernel.
- Problem Exporting PDFs:  When creating the pdf, go to the location of the file in your terminal and enter the following:
  1. export PATH=/Library/TeX/texbin:$PATH
  2. jupyter nbconvert your_notebook.ipynb --to pdf

   Here is the [Link for the stack overflow description](https://stackoverflow.com/questions/52300242/solving-500-internal-server-error-nbconvert-failed-xelatex-not-found-in-path)


### Mac Flopy install:
- If you get an error about missing .h files it could be that your headers are not installed. You can fix that following [these instructions](https://donatstudios.com/MojaveMissingHeaderFiles).
- also check that you have a recent version of  gfortran installed and reinstall if  needed per the first step in the instruction

____
<a name="github"></a>
## Getting Started - Homework and GitHub Classroom
1. I  will give you a link to an assignment, either through email or the class page. This will happen for each new assignment. You should follow the instructions for getting the homework repository set up. You should now have a repository for this homework.  

      Note: After you accept an assignment for the first time, we will send you an invite to join the classroom organization as a member. Please accept this. You will probably get an email with the invitation, but you should also see a link at the top of your main GitHub page. Here is an image of what you should see after clicking the link:

2. Enter the homework repository on GitHub (this is online--GitHub is different from Git!). Click “Clone or Download”, and make sure it says “Clone with SSH” in bold in the top left of the pop-up box. If not, click on the blue “Use SSH” button on the top right of the pop-up box. Now copy the link in the box to your clipboard.

3. Navigate inside of your homeworks directory and then type `git clone repository-link` where *repository-link* should be replaced with the link you copied to your clipboard in step 3. You now have the files.

      Note: If you received an error in the above steps, you may have to clone with HTTPS instead of SSH. You can do this by again clicking on the "Clone or Download" button in the repository page, then clicking "Use HTTPS" in the top right of the pop-up box. Now copy the link and repeat this step.

4. After you make changes to the homework assignment, commit them.  Commits are essentially taking a snapshot of your projects. For example, if I make changes to a code so that it prints "Hello world", and then commit them with an informative message, I can look at the history of my commits and view the code that I wrote at that time. If I made some more changes to the function that resulted in an error, I could go back to the commit where the code was originally working. This prevents you from creating several versions of your homework (homework-v1, homework-v2, ...) or from trying to remember what your code originally looked like.

      You can do commits through Atom if this is the text editor you are using or you can do it through command line. To do it through command line navigate to the homework directory. The type:
      `git add -A`
      `git commit -m "My commit message"`
      Git add is a command that tells git which files you want to record the changes to when you make your commit. For example, if I made changes to file1 and file2 since my last commit, I can choose to only commit (take a snapshot of) the changes I made to file1. git add -A says to add all of the files that have changed since the last commit. If I just want to add file1, I would instead type git add file1.

      Two things about committing. One, you should commit somewhat frequently. At minimum, if you're doing a homework assignment, you should make a commit each time that you've finished a question. Two, leave informative commit messages. "Added stuff" will not help you if you're looking at your commit history in a year. A message like "Added initial version of hello-world function" will be more useful.

5. At some point you'll want to get the updated version of the assignment back onto GitHub, either so that teachers/TAs can help you with your code, or so that it can be graded. You can do this by using a command called `git push` from inside your working directory. After you do this you should be able to see your latest changes on your git repo online.

____
<a name="additionalsoftware"></a>
## Optional additional software to install:
1. **Atom text editor** - This is a great text editor that has GitHub integration. <https://atom.io/>
2. **GitHub Desktop** - A GUI tool for downloading and managing git repos. <https://desktop.github.com/>
3. **GitKraken** – A tool for managing GitHub repos (Note the free version won't do private repos) <https://www.gitkraken.com/download>
4.	**ModelMuse** – For viewing MODFLOW models (Note you have to have windows for this to work). <https://www.usgs.gov/software/modelmuse-a-graphical-user-interface-groundwater-models>
