---
title: Setup
---

This lesson is designed to be run on a personal computer.
All of the software and data used in this lesson are freely available online,
and instructions on how to obtain them are provided below.

# <a name=#setup>Setup</a>

To participate in this lesson, we will use [Colab notebooks](https://colab.research.google.com/). Colab is a cloud-based environment where you can run scripting languages such as Python, create small segments of code, annotate them with notes and rich text, and return to your work later.

We will need to import our own resources into Colab, such as our simulated data. In order to do this, we will use Google drive. Because we will need to grant Colab access to our Google Drive data, **we strongly recommend creating an ad-hoc ("throwaway") Gmail account.** That way, we do not risk sharing or altering any sensitive data that we might have on our Broad Institute Google accounts.


## Obtain lesson materials

1. Download [this zip file][dataset] and save it to your Desktop. 
1. Unzip the ```data.zip``` file, which should create a new folder called ```data```.
1. Create a new folder in your home directory called ```lc-python``` and put the ```data``` folder in this folder.
1. Log into [Google Drive](https://drive.google.com/drive/my-drive) using the Gmail account you created for this course. You may want to use a private browsing window to do this if you usually use your Broad account when logging in to Drive.
1. Upload the lesson content by clicking "+ New" followed by "Folder upload." Select and upload the `lc-python` folder you just created.

You should see a `lc-python` folder in "My Drive", with a subfolder called `data`.


:::::::::::::::::::::::::::::::::::::::::: spoiler

## Further reading: colab alternatives

We chose Google colab to ensure Python setup and everyone's Jupyter interface would be consistent. For your personal use, you may prefer not to use colab. Below are colab alternatives that you might consider post-workshop.

## Python interfaces

To start working with Python, we need to launch a program that will interpret and execute our
Python commands. For our purposes today, we will use Colab, so you do not need to read further right now. However, if you want to do more with Python, you have a variety of options. It is a good idea to try out several of these interfaces to get a sense of which you prefer.

## Jupyter Notebook

A Jupyter Notebook provides a browser-based interface for working with Python. Colab is one example of this.
If you install Anaconda, you can launch a notebook in two ways:

::::::::::::::::: spoiler

## Anaconda Navigator

1. Launch Anaconda Navigator.
  It might ask you if you'd like to send anonymized usage information to Anaconda developers:
  ![](fig/anaconda-navigator-first-launch.png){alt='Anaconda Navigator first launch'}
  Make your choice and click "Ok, and don't show again" button.
2. Find the "Notebook" tab and click on the "Launch" button:
  ![](fig/anaconda-navigator-notebook-launch.png){alt='Anaconda Navigator Notebook launch'}
  Anaconda will open a new browser window or tab with a Notebook Dashboard showing you the
  contents of your Home (or User) folder.
3. Navigate to the `data` directory by clicking on the directory names leading to it:
  `Desktop`, `swc-python`, then `data`:
  ![](fig/jupyter-notebook-data-directory.png){alt='Anaconda Navigator Notebook directory'}
4. Launch the notebook by clicking on the "New" button and then selecting "Python 3":
  ![](fig/jupyter-notebook-launch-notebook.png){alt='Anaconda Navigator Notebook directory'}

:::::::::::::::::::::::::

::::::::::::::::: spoiler

## Command line (Terminal)

1\. Navigate to the `data` directory:

::::::::::::::::: spoiler

## Unix shell

If you're using a Unix shell application, such as Terminal app in macOS, Console or Terminal
in Linux, or [Git Bash][gitbash] on Windows, execute the following command:

```bash
cd ~/Desktop/swc-python/data
```

:::::::::::::::::::::::::

::::::::::::::::: spoiler

## Command Prompt (Windows)

On Windows, you can use its native Command Prompt program.  The easiest way to start it up is
pressing <kbd>Windows Logo Key</kbd>\+<kbd>R</kbd>, entering `cmd`, and hitting
<kbd>Return</kbd>. In the Command Prompt, use the following command to navigate to
the `data` folder:

```source
cd /D %userprofile%\Desktop\swc-python\data
```

:::::::::::::::::::::::::

2\. Start Jupyter server

::::::::::::::::: spoiler

## Unix shell

```bash
jupyter notebook
```

:::::::::::::::::::::::::

::::::::::::::::: spoiler

## Command Prompt (Windows)

```source
python -m notebook
```

:::::::::::::::::::::::::

3\. Launch the notebook by clicking on the "New" button on the right and selecting "Python 3"
from the drop-down menu:
![](fig/jupyter-notebook-launch-notebook2.png){alt='Anaconda Navigator Notebook directory'}

:::::::::::::::::::::::::

  <!-- vertical spacer -->

## IPython interpreter

IPython is an alternative solution situated somewhere in between the plain-vanilla Python
interpreter and Jupyter Notebook. It provides an interactive command-line based interpreter with
various convenience features and commands.  You should have IPython on your system if you installed
[Anaconda][anaconda-instructions].

To start using IPython, execute:

```source
ipython
```

  <!-- vertical spacer -->

## plain-vanilla Python interpreter

To launch a plain-vanilla Python interpreter, execute:

```source
python
```

If you are using [Git Bash on Windows][gitbash], you have to call Python *via* `winpty`:

```source
winpty python
```

::::::::::::::::::::::::::::::::::::::::::

[anaconda-instructions]: https://carpentries.github.io/workshop-template/install_instructions/#python
[dataset]: episodes/files/data.zip
[gitbash]: https://gitforwindows.org
