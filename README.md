# Space Science

This repository is for learning "Space Science" with Python.

The basic articles, which this repository for learning `Space Science` via `Python` is based on, were created by [Thomas Albin](https://twitter.com/MrAstroThomas)
and made available as a separate [SpaceScienceTutorial](https://github.com/ThomasAlbin/SpaceScienceTutorial) Git repository.
This is used as a tutorial basis and is divided into several subunits.
The naming may vary from the original tutorial.

## Getting Started

### Python Setup

First, you need to set up a virtual environment for Python.
For this, I used the `Anaconda` Python distribution.
If you are using `PyCharm` you can easily add a new virtual environment through the "Python Interpreter" settings.
Otherwise, you can manually do so by executing the following steps:

#### 1. Check If Conda Is Installed

```bash
$ conda -V
conda 23.1.0
```

#### 2. Update Conda If Not Up To Date

```bash
conda update conda
```

#### 3. Create A Virtual Environment For The Project

```bash
conda create -n yourenvname python=x.x anaconda
```

Where `x.x` is your desired Python version. This procedure can take some time.

#### 4. Activate The Virtual Environment

```bash
source activate yourenvname
or
conda activate yourenvname
```

#### 5. Install Python Packages To The Virtual Environment

```bash
conda install -n yourenvname [package]
```

### Install `Science Suite Packages` and `SPICE`

The following Python packages should be installed at the beginning because of their frequent usages:

```bash
conda install -n space-science numpy scipy matplotlib ipython jupyter pandas sympy nose
or
pip install numpy scipy matplotlib ipython jupyter pandas sympy nose
```

In addition, the NASA toolkit `SPICE` (_Spacecraft Planet Instrument C-matrix Events_) must be installed, as it is an essential part of this project.
This toolkit is used by most of the solar system science community to determine planet positions, asteroid coordinates in the night sky and much more.

[NASA SPICE](https://naif.jpl.nasa.gov/naif/index.html) provides some documentation, presentations and tutorials.

```bash
conda install -n space-science spiceypy
or
pip install spiceypy
```

## `SPICE` Introduction

SPICE was developed to provide planetary scientists and engineers with a common set of tools for computing various space-related information, such as:

* Positions and velocities of planets, satellites, comets, asteroids and spacecraft
* Size, shape and orientation of planets, satellites, comets and asteroids
* Orientation of a spacecraft and its various moving structures
* Instrument field-of-view location on a planet’s surface or atmosphere
* Time Conversion

SPICE does not compute computationally intensive tasks, but uses existing data to access a variety of problems related to the solar system.
Here SPICE cannot calculate much by itself and is dependent on auxiliary data sources, so-called `kernels`.
These are divided into different categories:

* **spk** - _spacecraft_ -  contain trajectory information of planetary bodies, spacecraft, etc.
* **pck** - _planet_ - contain physical parameters of bodies like the size or orientation
* **ik** - _instrument_ - contain instrument-specific information that are e.g., mounted on a spacecraft
* **ck** - _camera-matrix_ - contain information regarding the orientation of a spacecraft in space
* **fk** - _others_ - contain reference frame information that is needed to calculate positions in a less common reference system
* **lsk** - _others_ - contain time information that is crucial to convert e.g., the UTC time into ephemeris time ET (a standard time format that is being used in space science and astronomy)

With a large number of missions, the information about planetary trajectories and more is split into different kernels to generate more specific data structures,
so that only the information needed is updated and only that information needs to be used for processing.
One example for this information splitting is shown in [SPICE Kernels](https://naif.jpl.nasa.gov/pub/naif/).
These provided kernels (e.g. from the Apollo missions or the Cassini spacecraft) will play an important role in this tutorial.
