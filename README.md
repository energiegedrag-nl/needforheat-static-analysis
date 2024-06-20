# NeedForHeat analysis tools for domestic energy data using static models
This repository contains source code for the NeedForHeat heat balance models and analysis tools, based on static models, e.g. using day totals. For analysis tools that use dynamic models, we refer to [needforheat-dynamic-analysis](https://github.com/energietransitie/needforheat-dynamic-analysis). 

## Table of contents
* [General info](#general-info)
* [Prerequisites](#prerequisites)
* [Deploying](#deploying)
* [Developing](#developing) 
* [Features](#features)
* [Status](#status)
* [License](#license)
* [Credits](#credits)

## General info

This repository contains the code (mostly in the for op JupyterLab python code) of the static analysis software. This software was developed in the context of [REDUCEDHEATCARB](https://edu.nl/gutuc), a research project in which we extend the dynamic models from [Twomes](https://edu.nl/9fv8w) and [Brains4Buildings](https://edu.nl/kynxd) with new dynamic models for ventilation and learning heat distribution systems characteristics. The static analysis software in this repository was created in an effort to test whether less complex static analysis models can deliver automated estimation of crucial parameters of buildings, installations and comfort needs in individual homes based on time-series monitoring data that are on par with the results based on more complex, dynamic models.

For the required field data, including metadata descriptions, we refer to [needforheat-dataset-reducedheatcarb2023](https://github.com/energietransitie/needforheat-dataset-reducedheatcarb2023)

## Prerequisites

We recommend to [install and use JupyterLab in a docker container on a server](https://github.com/energietransitie/needforheat-server-configuration#jupyterlab).

As an alternative, you can use a [JupyterLab](https://jupyter.org/) environment on your local machine. Other environments, such as [PyCharm](https://www.jetbrains.com/pycharm/download/#section=windows) and [Visual Studio Code](https://code.visualstudio.com/) may work as well, but we do not include documentation for this here. 

To use JupyterLab on your local machine, make sure you have the following software properly installed and configured on your machine:

### Step 1: Install Python
If you haven't already installed it, go to [Python](https://www.python.org/downloads/) and install at least version 3.8, which includes `pip`, the package manager you need in the steps below.

### Step 2: Install and Launch JupyterLab

If you haven't already installed JupyterLab, you can [install JupyterLab](https://jupyter.org/install#jupyterlabl) with the following pip command in your terminal:

```
pip install jupyterlab
```

To add support for git from within the JupyterLab environment, issue the following command in your terminal:
```
pip install jupyterlab-git
```

Once you've installed JupyterLab, you can launch JupyterLab by running the following command in your terminal:

> **Note**
> In the step after this, we explain how to clone this repository from within jupyter-lab.
> If you are working locally and are familiar with using git, you can manually clone this repository,
> and open a terminal in the cloned directory before running the command below. You can then skip step 3.

```
jupyter-lab
```

This will open JupyterLab in your default web browser. 
### Step 3: Clone this Repository

In JupyterLab, navigate to the folder where you would like to clone this repository, select the git-icon in the left pane, select `Clone a Repository` and pase the URI for this repository, which is available via the green `<> Code` button on the GitHub page of this repository.

### Step 4: Install the Required Dependencies

After cloning this this respository, install requirements: open a terminal in JuypyterLab (available via the JupyterLab Launcher, via the `+` tab), navigate to the root folder of your clone of this repository and enter this command: 
  ```shell
  pip install -r requirements.txt
  ```  

This will install all the required dependencies listed in the [`requirements.txt`](requirements.txt) file.

## Deploying

This section describes how you can use the IPython notebooks, without changing the Python code. After installing JupyterLab as described above, you can run the software by opening Jupyter notebook `.ipynb ` files and run the contents. 

> N.B. To run the various Jupyter notebooks, you typically need to upload one or more parquet files to your JupyterLabs environment. After re-identification checks in late 2024, these will become available via [needforheat-dataset-reducedheatcarb2023](https://github.com/energietransitie/needforheat-dataset-reducedheatcarb2023). If you need the files before this moment, contact the product owner to see if you are eligible to work with the files.
> * [`needforheat_export_student.parquet`](https://github.com/energietransitie/needforheat-dataset-reducedheatcarb2023/blob/main/raw-measurements/needforheat_export_student.parquet)
> * [`remeha_export_student.parquet`](https://github.com/energietransitie/needforheat-dataset-reducedheatcarb2023/blob/main/raw-measurements/remeha_export_student.parquet)
> * [`weather_interpolation_locations.parquet`](https://github.com/energietransitie/needforheat-dataset-reducedheatcarb2023/blob/main/raw-measurements/weather_interpolation_locations.parquet)
> * `reducedheatcarb_sane_measurements_students_data_science.parquet`
> * `floor_area__m2`
   
Using the notebooks mentioned below, you can perform various analysis:
1. For general data understanding, run [avg temp and g_use per day per id, data understanding.ipynb](/avg%20temp%20and%20g_use%20per%20day%20per%20id%2C%20data%20understanding.ipynb)
2. To estimate the specific heat loss coefficienct H [W/K] per home, assuming no influence by solar heat gains, run WHICH_NOTEBOOK_TO_RUN
3. To estimate the specific heat loss coefficienct H [W/K] per home, assuming an average solar aperture of 26.8 [m²], run WHICH_NOTEBOOK_TO_RUN
4. To calculate realistic energy label, assuming standardized climate reference year and standardized comfort needs and other occupant behaviour, run WHICH_NOTEBOOK_TO_RUN.



## Developing

This section describes how you can change the source code. You can do this using JupyterLab, as described in the section [Deploying](#deploying). Other development environments, such as [PyCharm](https://www.jetbrains.com/pycharm/download/#section=windows) and [Visual Studio Code](https://code.visualstudio.com/) may work as well, but we do not include documentation for this here. 

Should you find any issues or bugs in our code, please report them via the [issues](https://github.com/energietransitie/needforheat-dynamic-analysis/issues) tab of this repository.

To change the code, we recommend:

* Try out your changes using the various `.ipynb ` files from the [`examples`](/examples) folder. The section [Deploying](#deploying) contains a high level description of these files.
* Migrate stable code to functions in Python files.
* Should you have extensions or bug fixes that could be useful for other users of the repository as well, please fork this reposotory and make a Pull Request on this repository. 

## Features

Current features include:
* awesome feature 1;
* awesome feature 2;
* awesome feature 3.

To-do:
* wow improvement to be done 1;
* wow improvement to be done 2.

## Status
Project is: _in progress_?

## License
This software is available under the [Apache 2.0 license](./LICENSE), Copyright 2024 [Research group Energy Transition, Windesheim University of Applied Sciences](https://windesheim.nl/energietransitie) 

## Credits
This software is a collaborative effort of:
* <contributor name 1> · [@Github_handle_1](https://github.com/<github_handle_1>) · Twitter [@Twitter_handle_1](https://twitter.com/<twitter_handle_1>)
* <contributor name 2> · [@Github_handle_2](https://github.com/<github_handle_2>) · Twitter [@Twitter_handle_2](https://twitter.com/<twitter_handle_2>)
* <contributor name 3> · [@Github_handle_3](https://github.com/<github_handle_3>) · Twitter [@Twitter_handle_3](https://twitter.com/<twitter_handle_3>)
* etc. 
* 
Thanks also go to:
* <thanks name 1> · [@Github_handle_1](https://github.com/<github_handle_1>) · Twitter [@Twitter_handle_1](https://twitter.com/<twitter_handle_1>)
* <thanks name 2> · [@Github_handle_2](https://github.com/<github_handle_2>) · Twitter [@Twitter_handle_2](https://twitter.com/<twitter_handle_2>)
* <thanks name 3> · [@Github_handle_3](https://github.com/<github_handle_3>) · Twitter [@Twitter_handle_3](https://twitter.com/<twitter_handle_3>)
* etc. 

Product owner:
* Henri ter Hofte · [@henriterhofte](https://github.com/henriterhofte) · Twitter [@HeNRGi](https://twitter.com/HeNRGi)

We use and gratefully acknowlegde the efforts of the makers of the following source code and libraries:
* [needforheat-dynamic-analysis](https://github.com/energietransitie/needforheat-dynamic-analysis), by Research group Energy Transition, Windesheim University of Applied Sciences, licensed under [Apache-2.0 License](https://github.com/energietransitie/twomes-analysis-pipeline/blob/main/LICENSE)
* [HourlyHistoricWeather](https://github.com/stephanpcpeters/HourlyHistoricWeather), by [@stephanpcpeters](https://github.com/stephanpcpeters), licensed under [an MIT-style licence](https://raw.githubusercontent.com/stephanpcpeters/HourlyHistoricWeather/master/historicdutchweather/LICENSE)

