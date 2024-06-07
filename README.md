# Image Quantification 101

## Python Setup

To ensure a smooth start into the Python session at ZIDAS 2024 we require you to prepare a conda environment. A conda environment is a special directory which contains all required dependencies to run Python and follow the planned Python session. Luckily you don't have to create this environment by hand. We will use the conda package manager to build the environment. If you have anaconda or miniforge already installed on your computer you can skip the first part and directly move on to the environment creation. Otherwise follow the miniforge install instructions first.

### Install miniforge
Miniforge is our recommended environment manager for Python environments. Please download the version which fits your operation system from [here](https://github.com/conda-forge/miniforge?tab=readme-ov-file#download) and follow the respective install instructions:
* [Windows](https://github.com/conda-forge/miniforge?tab=readme-ov-file#windows)
* [MacOS with Homebrew](https://github.com/conda-forge/miniforge?tab=readme-ov-file#homebrew)
* [MacOS & Linux](https://github.com/conda-forge/miniforge?tab=readme-ov-file#windows)

On MacOS and Linux close the terminal and reopen a new one. On Windows look for `Miniforge Prompt` in the start menu. 

You should be able to type `conda` into your terminal/Miniforge Prompt and see the following output:
```
usage: conda [-h] [-v] [--no-plugins] [-V] COMMAND ...

conda is a tool for managing and deploying applications, environments and packages.

options:
  -h, --help          Show this help message and exit.
  -v, --verbose       Can be used multiple times. Once for detailed output, twice for INFO logging, thrice for DEBUG logging, four times for TRACE logging.
  --no-plugins        Disable all plugins that are not built into conda.
  -V, --version       Show the conda version number and exit.

commands:
  The following built-in and plugins subcommands are available.

  COMMAND
    activate          Activate a conda environment.
    clean             Remove unused packages and caches.
    compare           Compare packages between conda environments.
    config            Modify configuration values in .condarc.
    create            Create a new conda environment from a list of specified packages.
    deactivate        Deactivate the current active conda environment.
    doctor            Display a health report for your environment.
    env               See `conda env --help`.
    info              Display information about current conda install.
    init              Initialize conda for shell interaction.
    install           Install a list of packages into a specified conda environment.
    list              List installed packages in a conda environment.
    notices           Retrieve latest channel notifications.
    package           Create low-level conda packages. (EXPERIMENTAL)
    remove (uninstall)
                      Remove a list of packages from a specified conda environment.
    rename            Rename an existing environment.
    repoquery         Advanced search for repodata.
    run               Run an executable in a conda environment.
    search            Search for packages and display associated information using the MatchSpec format.
    update (upgrade)  Update conda packages to the latest compatible version.

```

### Create ZIDAS2024 Environment
Download the Python setup material from [here]() and unpack it. You should see the following files:
* conda-linux-64.lock
* conda-osx-64.lock
* conda-osx-arm64.lock
* conda-win-64.lock

These are solved environment lock files containing a explicit list of packages and versions which we want to be installed in our environment. You can open them with a text editor (e.g. notepad), but you must not edit them!

Now you want to change to the directory where you put the `.lock` files. If you extracted the setup material in your `Downloads` directory you would now change to `Downloads/python_setup`.

__Windows:__ `dir Downloads/python_setup`
__MacOS/Linux:__ `cd Downloads/python_setup`

Now we can create the environment with conda from the respective lock-file. Please make sure that you choose the lock-file which fits to your operating system:
* Windows: `conda create -n zidas2024 --file conda-win-64.lock`
* MacOS: `conda create -n zidas2024 --file conda-osx-64.lock`
* MacOS Apple Silicon e.g. M1/M2: `conda create -n zidas2024 --file conda-osx-arm64.lock`
* Linux: `conda create -n zidas2024 --file conda-linux-64.lock`

Executing this command might take some time, but once it finishes you should see the following:
```
Downloading and Extracting Packages:

Preparing transaction: done
Verifying transaction: done
Executing transaction: done
```

To verify that everything worked run the following two commands:
```
conda activate zidas2024
napari
```

This should open the napari viewer after a little bit of waiting time. 

## To cite
If you use the exercise notebooks from this tutorial, please acknowledge it as follows:

Buchholz, T.-O., Witz, G., Uhlmann, V. (2024). Image Quantification 101 Tutorial. github.com/uhlmanngroup/imagequantification101

## Further resources
* Miura, K. & Sladoje, N. (2020). Bioimage Data Analysis Workflows. doi.org/10.1007/978-3-030-22386-1
* Bankhead, P. (2022). Introduction to Bioimage Analysis. bioimagebook.github.io
* Holmes, S. & Huber, W. (2018). Modern Statistics for Modern Biology. www.huber.embl.de/msmb

## Acknowledgements
Part of the material from this tutorial was adapted from Paula Balcells' Bachelor Thesis work carried out in the Uhlmann group.
