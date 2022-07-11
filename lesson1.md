# Lesson 1: Familiarizing Yourself with your Computing Environment

When a person thinks of sports analytics, the first thing that comes to mind is statistics. And this is rightfully so. However, almost an equal part of the job is being able to statistics at scale, and computers are great for this. With computing becoming more powerful and useful across all domains, it is imperative that a sports analyst is comfortable on the computer. 

## Operating Systems

A computer's operating system is what controls and manages your computer. When you open your laptop, you're meet with a nice GUI (graphical user interface) that is very intuitive to work with. You can see and click on all your folders and documents on the desktop and open them from there. But this is just exacctly what the acronym GUI stands for - an interface that makes it easier for the user to connect with the computer. If you want better control of your computing environment, you're going to need to get familiar with the command line.

### Command Line

The command line (or shell, terminal, prompt, etc.) is a text interface with your computer. On a Mac, it's called the terminal. You can access it by typing 'terminal' in spotlight search:

<img width="1440" alt="SAL1_1" src="https://user-images.githubusercontent.com/46616766/176978795-33018bfe-89ab-4df1-992a-59ba07d57aab.png">

*my terminal might look a little fancier than yours because of a an open-source design plugin called Oh-My-Zsh I installed

<img width="1440" alt="SAL1_2" src="https://user-images.githubusercontent.com/46616766/176978804-349d5a6b-03fd-4db8-8880-e2abeaeb832f.png">

Anything you can normally do on a computer you can do with the terminal. Open a text file, search a directory, open your favorite web browser. 

<img width="691" alt="SAL1_3" src="https://user-images.githubusercontent.com/46616766/176979215-db0e6f62-2b78-40a3-a20d-3f2a0ab2d813.png">

You can do much more with it though! You're data, tools, and code have to be stored somewhere on your computer and creating a clean workspace you're familiar with is vital.

## Important Bash Commands

The first and most important commands you learn are:
'cd' - change directory
'ls' - list directories

Let's see what directories are in your 'Documents' folder (if you have one):
```console
cd ~/Documents
ls
```
These two commands will help you navigate your computers file structure

## Setting up Your Python Environment

Using the command line, we can install Python and set up a workspace for us to code. The Mac OS actually comes pre-installed with Python 2.7, but it's an outdated version now and it's necessary to install Python 3. There are many ways one can set up their environment, and the way I'm about to describe is not the only way. 

First, a package manager. I recommend [Homebrew](https://mac.install.guide/homebrew/index.html). All you really need to do is run this in the terminal - it should take a few minutes to finish:

```console 
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```

Now back to Python. We need to be able to install and work with different versions of Python. To do this, we will enlist the help of a useful package called [pyenv](https://github.com/pyenv/pyenv#uninstall-python-versions). 

```console 
brew install pyenv
```
Now there are just a few commands we have to run to get pyenv working properly. We'll discuss this more in a minute, but first we have to find out what 'language' your terminal (also known as a shell) is running. To do so, run

```console 
echo $0
```
This should output either "-zsh" or "-bash", indicating ZShell or Bash respectively. 

For Bash, run these commands in the terminal:
```console
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.bashrc
echo 'command -v pyenv >/dev/null || export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.bashrc
echo 'eval "$(pyenv init -)"' >> ~/.bashrc
```

For Zsh, run these commands in the terminal:
```console
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.zshrc
echo 'command -v pyenv >/dev/null || export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.zshrc
echo 'eval "$(pyenv init -)"' >> ~/.zshrc
```

For the changes to take effect, run 
```console
exec "$SHELL"
```
Now we can install different python versions. For the purposes of this tutorial, we will install Python 3.7
```console
pyenv install 3.7.13
```
Pyenv has many different neat features, including the fact that we can easily set different project directories (folders) to "run" different python versions. For simplicity, we'll change the global default python version to our newly-installed version.
```console
pyenv global 3.7.13
```
Now we're all set with a new up-to-date Python version

### Quick aside: your shell language

What's a shell? What language does it run? What does that even mean?

Just like how there are many different coding languages besides Python, the terminal can read different types of languages. The most common are Bash and ZShell.

We call it a "shell" because you can think of the terminal as a "shell" around the operating system of the computer, thought of as the "kernel". The name "shell" for a command line interpreter and the concept of making the shell a user program outside of the operating system kernel were introduced in Unix's precursor Multics.

## Virtual Environments

There's a lot of power in Python by itself, but developers have already created fast, highly-optimized packages for others to use. One can only get so far without using important packages like Numpy, Scipy, Pandas, and more in the data science world. As a person grows to use more and more of these packages though, they don't always play nicely with each other. So basically, you can think of a virtual environment as an isolated place where we can keep many packages together. We can have several virtual environments, with each one having specific versions of packages that we may need for a specific project.

The most common (and arguably natural) way is to then store all of one's virtual environments in one place; i.e. under a folder titled virtualEnvs (or any other name). Do you remember how to create a directory?

```console
mkdir ~/virtualEnvs
```
Now to actually make the environment. Python comes with a pre-installed command to easily create virtual environments- [venv](https://docs.python.org/3/library/venv.html). If we want to create a virtual environment firstEnv, run:

```console
python3 -m venv ~/virtualEnvs/firstEnv
```

As we may have many different virtual environments, we need to activate it to work in it. 
```console
source ~/virtualEnvs/firstEnv/bin/activate
```
Now we're ready to install useful packages!

## Jupyter Notebooks

So now that we've got Python installed, how can we actually code in it? The simplest way is to just run the command 'python' in the terminal and this will create an interactive shell for you to code in! In simpler terms, once you tell the computer 'python', the computer now knows to interpret everything you type as a Python command.

<img width="689" alt="SAL_4" src="https://user-images.githubusercontent.com/46616766/176983388-4d284448-7ea6-4da3-a49c-8ea1e4fe5b3e.png">

For complex projects this is not practical. There are many different good code editors (like VSCode), but a good interactive IDE (integrated development environment) to start with is Jupyter Notebook. 

```console
pip3 install jupyter
```
To run it, just type 'jupyter notebook' to the console and create a new file (don't forget to activate your virtual environment!):

<img width="1440" alt="SAL_5" src="https://user-images.githubusercontent.com/46616766/176983712-af3a68c1-10b2-4cfa-878f-5212079b9d31.png">

## Creating your Project Directory

But where are these files stored? As you write and save more and more files, it's useful to keep them organized in a nice structure. For that, we will create a specific directory (folder) to store our files in.

For now, we will create a new folder on your Desktop called firstProject. The 'mkdir' bash command does exactly that, it creates a new folder in your current working directory (the folder that you are currently in).

```console
cd ~/Desktop
mkdir firstProject
```

When working with the jupyter notebook program, we can start it and then create a new 'notebook' (a special type of file with a .ipynb extension specific to the program). But what would are next steps be if we did not want to create a file through Jupyter Notebook? 

We need to create a python file to write our python code. We do this by creating a regular text file with the extension .py . This tells the computer that this type of file holds python code. To create a text file in Bash, use the 'touch' command followed by the name of the file you want to create.

```console
cd firstProject
touch firstPythonFile.py
```

We can edit this file using any text editor - Jupyter Notebook is an example of one! A text editor is just a program that let's you more easily write to a file (think of how you use Microsoft Word to write an essay). To run the file, we first tell the computer we want to use python and then the file name:

```console
python3 firstPythonFile.py
```

And that's how you run your first python file!

### Example Exercises

1) Create a new directory called passingProject (you can put it wherever you'd like; e.g. on your Desktop, in your Documents, etc)
2) Download the nflfastR.csv from your email and move it to your new directory 
   
   *hint - you might find the command listed here https://algodaily.com/lessons/bash-commands-cheat-sheet1*
   
Ready to learn more about Python? A good introduction - https://docs.python.org/3/tutorial/introduction.html

Python dictionaries - https://www.w3schools.com/python/python_dictionaries.asp

Python zip function - https://www.programiz.com/python-programming/methods/built-in/zip

3) A bunch of players have switched teams, and I want to find out which quarterback plays for the New York Giants. Given is a dictionary of players with their new teams as values (stored as their abbreviations). Print out who is the new quarterback of the Giants (NYG).

```python 
players = ['Brady', 'Murray', 'Mahomes', 'Allen', 'Tagovailoa']
teams = ['NYJ', 'ARI', 'IND', 'NYG', 'PHI']
new_dict = dict(zip(players,teams))
```

### Resources
Guide to VIM - https://linuxfoundation.org/blog/classic-sysadmin-vim-101-a-beginners-guide-to-vim/

Useful bash commands - https://www.educative.io/blog/bash-shell-command-cheat-sheet

The Linux command line for beginners - https://ubuntu.com/tutorials/command-line-for-beginners#1-overview

Venv documenation - https://docs.python.org/3/library/venv.html

Jupyter notebook guide - https://jupyter-notebook-beginner-guide.readthedocs.io/en/latest/what_is_jupyter.html

Pandas: Useful python library used for (effectively) creating and manipulating tables of data - https://pandas.pydata.org/docs/user_guide/10min.html
