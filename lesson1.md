# Lesson 1: Familiarizing Yourself with your Computing Environment

When a person thinks of sports analytics, the first thing that comes to mind is statistics. And this is rightfully so. However, almost an equal part of the job is being able to statistics at scale, and computers are great for this. With computing becoming more powerful and useful across all domains, it is imperative that a sports analyst is comfortable on the computer. 

## Operating Systems

*unfortunately this guide is tailored to Mac and Linux users. Windows users...sorry*

A computer's operating system is what controls and manages your computer. When you open your laptop, you're meet with a nice GUI (graphical user interface) that is very intuitive to work with. You can see and click on all your folders and documents on the desktop and open them from there. But this is just exacctly what the acronym GUI stands for - an interface that makes it easier for the user to connect with the computer. If you want better control of your computing environment, you're going to need to get familiar with the command line.

### Command Line

The command line (or shell, terminal, prompt, etc.) is a text interface with your computer. On a Mac, it's called the terminal. You can access it by typing 'terminal' in spotlight search:

<img width="1440" alt="SAL1_1" src="https://user-images.githubusercontent.com/46616766/176978795-33018bfe-89ab-4df1-992a-59ba07d57aab.png">

*my terminal might look a little fancier than yours because of a an open-source design plugin called Oh-My-Zsh I installed

<img width="1440" alt="SAL1_2" src="https://user-images.githubusercontent.com/46616766/176978804-349d5a6b-03fd-4db8-8880-e2abeaeb832f.png">

Anything you can normally do on a computer you can do with the terminal. Open a text file, search a directory, open your favorite web browser. 

<img width="691" alt="SAL1_3" src="https://user-images.githubusercontent.com/46616766/176979215-db0e6f62-2b78-40a3-a20d-3f2a0ab2d813.png">

You can do much more with it though! You're data, tools, and code have to be stored somewhere on your computer and creating a clean workspace you're familiar with is vital.

## Creating your Project Directory

Now that we have python installed, 

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

### Understanding your shell language

Bash, Zsh

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

### Virtual Environments

There's a lot of power in Python by itself, but a lot of developers have already created fast, highly-optimized packages for others to use. One can only get so far without using important packages like Numpy, Scipy, Pandas, and more in the data science world. As a person grows to use more and more of these packages though, they don't always play nicely with each other. So basically, you can think of a virtual environment as an isolated place where we can keep many packages together. We can have several virtual environments, with each one having specific versions of packages that we may need for a specific project.

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

### Jupyter Notebooks

So now that we've got Python installed, how can we actually code in it? The simplest way is to just run the command 'python' in the terminal and this will create an interactive shell for you to code in! In simpler terms, once you tell the computer 'python', the computer now knows to interpret everything you type as a Python command.

<img width="689" alt="SAL_4" src="https://user-images.githubusercontent.com/46616766/176983388-4d284448-7ea6-4da3-a49c-8ea1e4fe5b3e.png">

For complex projects this is not practical. There are many different good code editors (like VSCode), but a good interactive IDE (integrated development environment) to start with is Jupyter Notebook. 

```console
pip3 install notebook
```
To run it, just type 'jupyter notebook' to the console and create a new file (don't forget to activate your virtual environment!):

<img width="1440" alt="SAL_5" src="https://user-images.githubusercontent.com/46616766/176983712-af3a68c1-10b2-4cfa-878f-5212079b9d31.png">




## Important Bash Commands

The first and most important commands you learn are 'cd' and 'ls'


```console
cd ~/Documents
```
With this
