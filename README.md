# HWRS 482/582 Applied Groundwater Modeling

This repo contains course materials for HWRS 482/582

__
## Repo Contents
- **Lectures** - Notes and slides from lectures will be posted as they are completed.
- **Homework_Keys** - Keys for graded homework assignments will be available in this directory after they are submitted.
- **References** - General Reference materials.

___
## Helpful Links and Tutorials
- **Flopy** <https://modflowpy.github.io/flopydoc/>
- **MODFLOW** <
- **Shell** <https://seankross.com/the-unix-workbench/command-line-basics.html#summary>
- **Jupyter**  <https://www.dataquest.io/blog/jupyter-notebook-tutorial/>
- **Markdown** <https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet>
____

## Getting Started - Software install instructions
For this class we will use the following software packages.  Please follow the following instructions to get this setup on your laptop.

1.	**Install Python3:** You can download this here. Make sure you pick the version that is right for your operating system <https://www.python.org/downloads/>

2.	**Install Python Packages:** After you have installed python you will need the following packages. These can be installed using the command `pip3 install modulename` from the command line where *modulename* is the name of the module from the list below:
  - jupyter
  - numpy
  - requests
  - flopy
  - matplotlib
  - Pandas

 To check if you have installed these modules you can use the command `pip3 list`. Alternatively if you prefer you can install module using [Andaconda] (https://www.anaconda.com/distribution/)

3.	**Setup account and install Github**
  - Register for account on GitHub: <https://github.com/>
  - Check if you have GitHub installed and if not install it.  Directions for both Windows & Mac here: <http://happygitwithr.com/install-git.html>. Windows users should follow Option 1 in 7.2. Mac users can follow Option 1 in 7.3 if comfortable, otherwise follow Option 2. Below,
  - Setup options in Git. In you have a Mac, you can go to the terminal if you have a Mac (Applications -> Utilities -> Terminal) as shown above. If you have a Windows, open Git BASH, which you should have downloaded in step 3.  You will need to  setup you username:  <https://help.github.com/en/github/using-git/setting-your-username-in-git> and your email: <https://help.github.com/en/github/setting-up-and-managing-your-github-user-account/setting-your-commit-email-address>
  - Generate a SSH key so you don’t need to enter your password every time you interact with GitHub. Instructions for this can be found here: <https://help.github.com/en/github/authenticating-to-github/adding-a-new-ssh-key-to-your-github-account>.


4.	**Setup a directory for this class and clone main repo**
  - Make a directory for this class wherever you would like to have it on your computer
  - Open a terminal window and navigate to your course directory (you can do this using the commands cd and pwd)
  - Clone the main course materials repo: `git clone https://github.com/groundwater-modeling-Spring2020/Course_Materials`

5.	**Install MODFLOW**  Run the following commands to install MODFLOW using the PyMake
  - `cd` to a directory where you would like to put your MODFLOW builds
  - `Pip3 install https://github.com/modflowpy/pymake/zipball/master`
  - `git clone https://github.com/modflowpy/pymake`
  - `cd pymake/examples`
  - `python3 make_mf2005.py`
  - `python3 make_mp7.py`
  - The mp7 and mf2005 folders created in this step have the mode executables that you will need to point to when you are running MODFLOW. If you want to move these somewhere else you can do so now.


#### Optional additional software to install:
1.	**GitKraken** – A tool for managing github repos <https://www.gitkraken.com/download>
2.	**ModelMuse** – For viewing MODFLOW models (Note you have to have windows for this to work). <https://www.usgs.gov/software/modelmuse-a-graphical-user-interface-groundwater-models>
