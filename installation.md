---
title: Installation
layout: default
permalink: /installation
---

# Installing Python Environments

This course uses multiple environments: instead of a single large environment, we use specialized environments for different course modules. This hopefully reduces conflicts and ensures reliable performance across Windows, macOS, and Linux.

| Environment | Weeks | Contents |
|---|---|---|
| `che155-core` | 1–6 | Data science and Python basics |
| `che155-quantum` | 8 | Psi4 (electronic structure) |
| `che155-dynamics` | 7, 9 | RDKit, OpenMM (molecular dynamics) |
| `che155-ml` | 10 | JAX/PyTorch (machine learning) |

Make sure your computer is plugged in and you have a reasonably fast Internet connection.

*Note:* The `che155-quantum` environment (Week 8) contains the `psi4` package, which is not available for Windows. Windows users will need to install this environment inside WSL (Windows Subsystem for Linux) for that week only. See [WSL Setup](#wsl-setup). The other three environments can be installed natively on Windows.

- [Windows](#windows)
- [MacOS & Linux](#macos-and-linux)
- [ChromeOS](#chromeos)
- [WSL Setup (Windows, Week 8 only)](#wsl-setup)
- [Running Jupyter Lab](#running-jupyter-lab)


## Windows

The core, dynamics, and ML environments can be installed natively on Windows. Only Week 8's quantum chemistry environment requires WSL.

**Step 1:** Visit the [Miniconda webpage](https://docs.conda.io/en/latest/miniconda.html) and download the **Windows 64-bit** installer. Run the installer and follow the on-screen prompts.

After installation, open the **Anaconda Prompt** (search for it in the Start menu). You should see `(base)` in your prompt.

*Note for existing Anaconda/Miniconda installations:* It is recommended to start with a fresh Miniconda installation to avoid solver conflicts. You can uninstall an existing installation from the Windows Control Panel before proceeding.

**Step 2:** Set up the faster libmamba solver. This prevents conda from hanging when creating large environments:

```
conda install -n base conda-libmamba-solver
conda config --set solver libmamba
```

**Step 3:** Download the environment files. In your Anaconda Prompt, run:

```
curl -O {{ site.url }}/che155/assets/text/che155-core.yml
curl -O {{ site.url }}/che155/assets/text/che155-dynamics.yml
curl -O {{ site.url }}/che155/assets/text/che155-ml.yml
```

**Step 4:** Create the environments. This is the longest step; each environment downloads and installs many packages. Allow 10–20 minutes per environment.

```
conda env create -f che155-core.yml
conda env create -f che155-dynamics.yml
conda env create -f che155-ml.yml
```

**Step 5:** Register the non-core environments as Jupyter kernels so you can switch between them within a single JupyterLab session:

```
conda activate che155-dynamics
python -m ipykernel install --user --name che155-dynamics --display-name "Python (CHE 155 Dynamics)"

conda activate che155-ml
python -m ipykernel install --user --name che155-ml --display-name "Python (CHE 155 ML)"
```

**Step 6 (Week 8 only):** For the quantum chemistry module, follow the [WSL Setup](#wsl-setup) instructions below.

Setup for Weeks 1–7 and 9–10 is complete! Move on to [Running Jupyter Lab](#running-jupyter-lab).

## MacOS and Linux

The instructions for macOS and Linux are grouped together because they are very similar in terms of the steps and the potential issues that could be encountered.

**Tip for organization:**
You can create a `CHE155` folder inside the `Documents` folder in your home folder, then enter it using `cd ~/Documents/CHE155` before downloading any files. Keeping your files in one place reduces the confusion that comes from having files in multiple locations.

**Step 1:** Download the Miniconda installer. Miniconda is a slimmed-down version of the Anaconda Python distribution that includes the `conda` package manager.

You may download from the [Miniconda webpage](https://docs.conda.io/en/latest/miniconda.html), or use the command line instructions below.

*For Mac*:
```
curl -O https://repo.anaconda.com/miniconda/Miniconda3-latest-MacOSX-x86_64.sh
```

*For Linux or WSL*:
```
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
```

*Note for Apple M1/M2/M3 Mac users:* You shouldn't download the Apple silicon installer because not all of the packages are available for that architecture. Instead, run your Terminal in "Rosetta" mode, which allows running programs built for Intel CPUs. Do this by going to Applications → Utilities, right-clicking Terminal, choosing "Get Info", and checking "Open in Rosetta".

*Note for existing Anaconda/Miniconda installations:* It is recommended to start with a brand-new Miniconda installation and remove any existing installation before proceeding, as this reduces the chance of conda getting stuck while solving environments. You can remove an existing installation by deleting the install folder (typically `~/miniconda3` or `~/anaconda3`). If you still want to use an existing installation, skip to Step 4.

**Step 2:** Install Miniconda by running the installer script:

`bash Miniconda3-latest-MacOSX-x86_64.sh` (Mac) or `bash Miniconda3-latest-Linux-x86_64.sh` (Linux/WSL).

When asked whether to initialize conda, say yes.

**Step 3:** Close and reopen the terminal. You should now see `(base)` in your prompt.

**Step 4:** Set up the faster libmamba solver to prevent conda from hanging on large environments:

```
conda install -n base conda-libmamba-solver
conda config --set solver libmamba
```

**Step 5:** Download the environment files.

*For macOS*:
```
curl -O {{ site.url }}/che155/assets/text/che155-core.yml
curl -O {{ site.url }}/che155/assets/text/che155-quantum.yml
curl -O {{ site.url }}/che155/assets/text/che155-dynamics.yml
curl -O {{ site.url }}/che155/assets/text/che155-ml.yml
```

*For Linux or WSL*:
```
wget {{ site.url }}/che155/assets/text/che155-core.yml
wget {{ site.url }}/che155/assets/text/che155-quantum.yml
wget {{ site.url }}/che155/assets/text/che155-dynamics.yml
wget {{ site.url }}/che155/assets/text/che155-ml.yml
```

**Step 6:** Create the conda environments. This is the longest step; each environment downloads and installs many packages. Allow 10–20 minutes per environment.

```
conda env create -f che155-core.yml
conda env create -f che155-quantum.yml
conda env create -f che155-dynamics.yml
conda env create -f che155-ml.yml
```

The output for each environment should look something like this:

<pre>
Collecting package metadata (repodata.json): done
Solving environment: done <b>(This could take a few minutes, but see me if it takes longer than 10 minutes.)</b>

Downloading and Extracting Packages
libclang13-14.0.6    | 10.6 MB   | ####################### | 100%
xcb-util-0.4.0       | 20 KB     | ####################### | 100%
lcms2-2.12           | 443 KB    | ####################### | 100%
libsndfile-1.0.31    | 602 KB    | ####################### | 100%
json5-0.9.5          | 20 KB     | ####################### | 100%
pygments-2.13.0      | 821 KB    | ####################### | 100%
libsodium-1.0.18     | 366 KB    | ####################### | 100%
prompt-toolkit-3.0.3 | 254 KB    | ####################### | 100%
<b>(Several dozen packages will be downloaded, some with >100 MB file sizes)</b>
Preparing transaction: done
Verifying transaction: done
Executing transaction: done
#
# To activate this environment, use
#
#     $ conda activate che155-core
#
# To deactivate an active environment, use
#
#     $ conda deactivate
</pre>

It is recommended to leave this running in the background; make sure your laptop is plugged in so the battery won't run out.

**Step 7:** Register the non-core environments as Jupyter kernels so you can switch between them within a single JupyterLab session:

```
conda activate che155-quantum
python -m ipykernel install --user --name che155-quantum --display-name "Python (CHE 155 Quantum)"

conda activate che155-dynamics
python -m ipykernel install --user --name che155-dynamics --display-name "Python (CHE 155 Dynamics)"

conda activate che155-ml
python -m ipykernel install --user --name che155-ml --display-name "Python (CHE 155 ML)"
```

Setup is complete! Move on to [Running Jupyter Lab](#running-jupyter-lab).

## ChromeOS

*Note: Many Chromebooks are just not suitable for running a Python environment, particularly those that have very limited hard disk space. It may not be possible to complete all of the coursework with a Chromebook! These instructions have not been extensively tested, so proceed at your own risk.

- **Step 1:** Follow the [Linux setup instructions](https://chromeos.dev/en/linux/setup) on the ChromeOS webpage.

- **Step 2:** Open the new Terminal app and follow the [Linux instructions](#macos-and-linux).

<a name="wsl-setup"></a>

## WSL Setup (Windows, Week 8 only)

Because `psi4` does not support Windows natively, Windows users need to install the quantum chemistry environment inside the Windows Subsystem for Linux (WSL).

**Step 1:** Visit the [Install WSL](https://docs.microsoft.com/en-us/windows/wsl/install-win10) page on Microsoft's website and read the Prerequisites and Install WSL sections.

Check if your Windows version meets the requirements (Windows 10 Build 19041 and higher, or Windows 11).
If your version of Windows is not recent enough, you may need to upgrade it before going to Step 2.

**Step 2:** Install WSL. Open Powershell as Administrator and run the command:

```
wsl --install --distribution Ubuntu-20.04
```

If it works, you will see several messages appear in Powershell (blue window in the image below), then a second window (Ubuntu, black window in the image below) will pop up.
After a while, the second window will prompt you for a username and password; it is convenient, but not required, to use the same username as your Windows account.
After entering your account info, the second window will give you a prompt to enter commands for your new Ubuntu operating system; keep in mind that this is a totally different environment from Windows Powershell, though they look similar.
In the future you can open the Ubuntu command line by running Ubuntu from the Start menu.

At this point it's best to restart your computer.

![Screenshot of Windows PowerShell running the WSL install command in the background, with the Ubuntu terminal open in the foreground showing the initial login prompt.]({{ site.baseurl }}/assets/images/installation/windows-install-wsl.png){: width="350"}

Above: Windows PowerShell (top) and Ubuntu terminal (bottom)

**Troubleshooting note:** What if you saw the error message, "The Virtual machine could not be started because a required feature is not installed"?

This error has been observed several times over past years on students' computers and the solution is to enable virtualization in the BIOS (built-in operating system). To enter the BIOS, restart the computer and press the key indicated on the first startup screen you see; this may be Del, F2, or something else (you may only have a few seconds to do so).
In the menu that appears, find the Virtualization menu item and enable the virtualization options for your CPU (probably Intel or AMD).
Then save the settings and exit, and your computer will be rebooted once more. You should no longer see the error when attempting to install WSL.

![Two screenshots of the ThinkPad BIOS Setup Security menu, showing the Virtualization submenu with Intel Virtualization Technology and Intel VT-d Feature enabled.]({{ site.baseurl }}/assets/images/installation/bios.jpg){: width="550"}

Above: Turning on virtualization on your instructor's laptop

<details closed>
<summary> What is Ubuntu? I thought we were installing Linux? (click to expand) </summary>

Ubuntu is a Linux distribution, i.e. one of several operating systems all running the Linux kernel.  The kernel is the heart of the OS that manages the computer hardware and all running programs, and is normally hidden from user interaction. <br/><br/>

In addition to the kernel, Ubuntu comes with various other software components, such as the "bash" shell (i.e. the terminal), the "apt" package manager, text editors, compilers, and many others.
It also has a graphical desktop called GNOME but WSL doesn't need it, because your graphical desktop is Windows itself. The package manager allows programs to be installed by downloading them from online repositories.<br/><br/>

Because our course is taught mostly as Python codes in Jupyter notebooks, we will mainly be using Ubuntu to run the programs "conda" and "jupyter".
You can also use another Linux distribution if you're feeling adventurous. They will have many common features but also important differences (one major difference will be the package manager and repositories).<br/>

</details><br/>

**Step 2a (optional):** Install the Windows terminal.

You can get the Windows terminal from the Microsoft store.
The Windows terminal allows you to open different command lines (such as Windows Powershell and Ubuntu), but it comes with convenient features such as tabs, a longer scrollback history, cut/paste, customizable colors, etc.

![Screenshot of Windows Terminal showing a PowerShell tab with the new-tab dropdown menu open, with Ubuntu-20.04 highlighted as an option, and an Ubuntu terminal tab open below.]({{ site.baseurl }}/assets/images/installation/windows-terminal.png){: width="350"}

When you open Windows Terminal for the first time, it will give you a Windows Powershell by default (above image).
You can open a Ubuntu terminal by clicking the small "⌄" icon in the menu bar.
Using the Settings you can also make Ubuntu the default terminal.

**Step 3:** Familiarize yourself with the WSL filesystem and how it is related to the Windows filesystem.

Your Ubuntu terminal has its own filesystem. In Linux operating systems the filesystem is a directory tree starting with `/` as the root. Hard drives can be *mounted* to directories allowing you to work with their contents. (I will often use the terms "folder" and "directory" interchangeably.)
The hard drive containing the Windows filesystem is mounted at `/mnt/c/`, and your Windows home folder is located at `/mnt/c/Users/win_username/` where `win_username` is your Windows user name.
On the other hand, your home folder in Ubuntu is located at `/home/ubuntu_username/` where `ubuntu_username` is what you provided during the installation.
To access your familiar Windows files, navigate to your Windows home directory as follows:

```
cd /mnt/c/Users/
```
and look for the folder that matches your username.

However, it is inconvenient to type `cd /mnt/c/Users/win_username/` every time you want to access your Windows files.
For convenience you may create symbolic links (shortcuts) from your Windows home folder into your Ubuntu home folder.
In the following list of commands, only the first `cd` and `ln -s` is essential and the others are instructive:

```
cd ~
pwd
ls
ln -s /mnt/c/Users/win_username/Documents ./Documents
ls
cd Documents
ls
```

Explanation of the above commands:
- `cd` changes directories and `~` is shorthand for your home folder.
- `pwd` prints the working directory, and should show that your current folder (in the Ubuntu filesystem) is `/home/ubuntu_username`.
- The first `ls` command will probably show that your brand-new home folder is empty. (Actually, there are hidden files whose names start with `.` and are not displayed by default with `ls`, but `ls -a` will reveal them.)
- `ln -s` creates symbolic links or shortcuts. In this case we are creating a link in your home folder that points to your Windows Documents folder. The `./` refers to the current folder (the home folder). You can omit it, but I generally like to explicitly refer to the current folder.
The second `ls` command lists the files in the home folder and you should now see the `Documents` link.
Because the `Documents` link is a shortcut to a folder, you can enter it with the `cd` command.
List the folder contents with `ls` to see your files stored in your Windows `Documents` folder.

*Note: The actual location of your Documents folder may depend on several factors, including whether you use cloud storage. Generally you can find the Windows path for a folder by clicking on the address bar in Windows Explorer, then the corresponding path in Ubuntu will be something like `/mnt/drive_letter/windows_path`. You can modify the above steps according to your needs.*

Your Ubuntu filesystem is also accessible from the Windows filesystem, but it is not easy to find in Windows Explorer.
To open an Explorer window into an Ubuntu folder, first `cd` into the folder in the terminal, then enter `explorer.exe` into the terminal.
A Windows Explorer window should pop up.
You can drag the folder to Quick Access to quickly return to the folder later.

**Tip for organization:**
To help keep your files organized, you can create a `CHE155` folder in `Documents` in your Windows home folder.
If you followed the above instructions, you should already have a `Documents` link in your Ubuntu home folder that points to your Windows `Documents` folder.
For any class-related activity, you can enter the folder by entering `cd ~/Documents/CHE155` in your Ubuntu terminal before running `jupyter` or anything else.

**Step 4:** Inside the Ubuntu terminal, download and install the Linux version of Miniconda, then follow the [MacOS and Linux instructions](#macos-and-linux) beginning with Step 1. When you reach Step 5, you only need to download and install `che155-quantum.yml`. Register the environment as a kernel:

```
conda activate che155-quantum
python -m ipykernel install --user --name che155-quantum --display-name "Python (CHE 155 Quantum)"
```

The quantum chemistry kernel will be available when you launch JupyterLab from your WSL terminal.

## Running Jupyter Lab

Jupyter Lab is a Python notebook environment that runs in your web browser. The `che155-core` environment contains the Jupyter Lab software configured with extensions for interactive graphics. The other environments are accessible from within a single JupyterLab session by switching kernels.

- **Step 1:** Open your terminal and activate the core environment:
```
conda activate che155-core
```

- **Step 2:** Launch JupyterLab:
```
jupyter lab
```

![Terminal output from running the 'jupyter lab' command, showing extensions loading successfully and the local URLs to open JupyterLab in a browser.]({{ site.baseurl }}/assets/images/installation/jupyter-lab.png){: width="650"}

This will spawn a Jupyter server instance and attempt to open your web browser. If it does not do so automatically, it will print a URL that you can copy and paste into your browser manually.

If your browser fails to connect to the URL, try this command instead:
```
jupyter lab --no-browser
```

- **Step 3:** To use a different environment for a particular notebook (e.g., the quantum chemistry environment for Week 8), click the kernel name in the top-right corner of the notebook and select the appropriate environment from the list.

*Note:* The above screenshot shows some warning and error messages. Although they appear to be concerning, they don't affect the use of Jupyter Lab. To open the notebook, you only need to visit the highlighted link.

Over time, you will become attuned to which warning/error messages are important and which ones are irrelevant. It is one of the most important, yet unspoken-of skills on your journey to becoming a programmer.

When you are finished working, it is best to shut down the Jupyter server by choosing `File > Shut Down` from the JupyterLab menu. Once you have done so, you can close the browser tab and close out your terminal session if desired.

*Final note:* As most of the instructions on this page refer to installation, you will only need to do them *once*.
However, take note of the actions you need to do repeatedly:
- If you close the terminal or restart your computer, you will need to reopen the terminal.
- Every time you reopen your terminal, you will need to enter `conda activate che155-core` to activate your environment.
- After activating the environment, you will need to enter `jupyter lab` to access your notebooks. If you close the terminal, it will stop the notebook server and the notebooks in your browser will no longer work.
- Avoid running `jupyter lab` in multiple terminals. Having multiple notebook servers running could lead to issues such as file access errors.
