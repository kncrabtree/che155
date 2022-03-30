---
title: Installation
layout: default
permalink: /installation
---

# Installing a Python Environment

This course will use a number of packages that are not included with a standard Python installation. For convenience, these are included in an [environment file]( {{site.baseurl}}/assets/text/environment.yml) that is compatible with the `conda` package manager. If you already have an existing Anaconda or Miniconda installation on your system, you may be able to simply install the new environment and use it (unless your operating system is Windows; more on this below). Alternatively, you can follow the instructions for your operating system below.

*Note:* This environment contains the `psi4` package, which is not available for Windows. If you are using Windows, then you will not be able to use an existing anaconda/miniconda installation, and you will need to follow the instructions below.

- [Windows](#windows)
- [MacOS](#macos)
- [Linux](#linux)
- [ChromeOS](#chromeos)
- [Running Jupyter Lab](#running-jupyter-lab)


## Windows

As noted above, the `psi4` package that we will use in the course is not available for Windows. However, there is a workaround that is straightforward: using the Windows Subsystem for Linux.

- **Step 1:** Activate the Windows Subsystem (WSL1) for Linux. The entire process is documented on [Microsoft's Website](https://docs.microsoft.com/en-us/windows/wsl/install-win10). All you need to do is open Powershell as Adminstrator and run the command:
```
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
```
Then restart your computer. Optionally, if your computer supports WSL2, you can follow the rest of the instructions on the website linked above and get a full Linux installation with a UI, then follow the [Linux instructions](#linux). However, not all computers support WSL2, so if you are unsure, please continue with these instructions.
*Note: if you already have a WSL1 installation you would like to use, open it and proceed to the [Linux instructions](#linux)).

- **Step 2:** Install [Ubuntu 20.04 LTS](https://www.microsoft.com/store/apps/9n6svws3rx71) from the Microsoft Store.

- **Step 3:** Open the Ubuntu 20.04 application, which will open a terminal on the screen. Follow the initial instructions to set up a user account.

- **Step 4:** You will want to create a symbolic link (shortcut) to your Windows user folder for convenience. Run the command
```
ll /mnt/c/Users
```
and look for the folder that matches your username (mine is `leeping`). Then create the link with the command
```
ln -s /mnt/c/Users/leeping c
```
replacing `leeping` with the username on your system. This will create a shortcut named `c`. Run the command `ll` to see that `c` points to the correct folder.

*Note: if you store your files elsewhere, such as an external hard drive, the disk drives that are mounted are available by letter in the `mnt` folder (e.g., `/mnt/d`, `/mnt/e`, etc.). You may create additional links to other drives as needed. The syntax is `ln -s target/folder linkName`.*

- **Step 5:** From this point, follow the [Linux instructions](#linux).

## MacOS

- **Step 1:** Open your Terminal program and download the latest version of miniconda with the command:
```
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-MacOSX-x86_64.sh
```
*Note:* if you already have a miniconda installation, skip to step 4.

- **Step 2:** Install miniconda by running the command
```
bash Miniconda3-latest-MacOSX-x86_64.sh
```
When asked if you want to activate the conda environment, say yes.

- **Step 3:** Close and reopen the Terminal program.

- **Step 4:** Download the environment file with the command
```
wget https://leeping.github.io/che155/assets/text/environment.yml
```

- **Step 5:** Install the conda environment:
```
conda env create -f environment.yml
```
Note: This step is known to take a very long time, especially at the `Solving environment...` step.  
A test run of the installation on your instructor's laptop took around 50 minutes. 
It is recommended to leave this running in the background. 

- **Step 6:** Activate the new `che155` environment:
```
conda activate che155
```

- **Step 7:** Install JupyterLab extensions
```
jupyter labextension install @jupyter-widgets/jupyterlab-manager jupyter-matplotlib nglview-js-widgets jupyterlab-plotly
```

Setup is complete! Move on to [Running Jupyter Lab](#running-jupyter-lab).

## Linux

- **Step 1:** Open a terminal. For Windows users on WSL1, this is done just by opening the Ubuntu 20.04 program. Download the miniconda installer with the command
```
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
```
*Note:* if you already have a miniconda installation, skip to step 4.

- **Step 2:** Install miniconda by running the command
```
bash Miniconda3-latest-Linux-x86_64.sh
```
When asked if you want to activate the conda environment, say yes.

- **Step 3:** Close and reopen the terminal. WSL1 users, simply close and reopen the Ubuntu 20.04 program. Your prompt will now begin with `(base)`.

- **Step 4:** Download the environment file with the command
```
wget https://leeping.github.io/che155/assets/text/environment.yml
```

- **Step 5:** Install the conda environment:
```
conda env create -f environment.yml
```
Note: This step is known to take a very long time, especially at the `Solving environment...` step.  
A test run of the installation on your instructor's laptop took around 50 minutes. 
It is recommended to leave this running in the background. 

- **Step 6:** Activate the new `che155` environment:
```
conda activate che155
```

- **Step 7:** Install JupyterLab extensions
```
jupyter labextension install @jupyter-widgets/jupyterlab-manager jupyter-matplotlib nglview-js-widgets jupyterlab-plotly
```

Setup is complete! Move on to [Running Jupyter Lab](#running-jupyter-lab).


## ChromeOS

*Note: Many Chromebooks are just not suitable for running a Python environment, particularly those that have very limited hard disk space. It may not be possible to complete all of the coursework with a Chromebook! These instructions have not been extensively tested, so proceed at your own risk.

- **Step 1:** Open the Settings menu and enable the Linux (beta) feature.

- **Step 2:** Launch the Linux beta program and follow the prompts.

- **Step 3:** From the Linux beta terminal, follow the [Linux instructions](#linux)

## Running Jupyter Lab

Jupyter Lab is a Python notebook environment that runs in your web browser. The `che155` environment that was created during the installation contains the Jupyter Lab software configured with extensions for interactive graphics.

- **Step 1:** Open your terminal and ensure the `che155` environment is active (`conda activate che155`).

- **Step 2:** Run the command
```
jupyter lab
```
This will spawn a jupyter server instance and attempt to open your web browser. If it does not do so automatically (e.g., WSL1 users), it will print a URL that you can copy and paste into your browser manually.

When you are finished working, it is best to shut down the jupyter server by choosing `File > Shut Down` from the JupyterLab menu. Once you have done so, you can close the browser tab and close out your terminal session if desired.
