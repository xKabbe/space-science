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

## Tutorials

| Step | Tutorial                             |                                                                                                                     |                                                                  |
|:----:|--------------------------------------|:-------------------------------------------------------------------------------------------------------------------:|:----------------------------------------------------------------:|
|  1   | `An Introduction`                    |          [Weblink](https://thomas-albin.medium.com/space-science-with-python-an-introduction-2de33e26c7b2)          |           [PDF](./doc/tutorials/1_an_introduction.pdf)           |
|  2   | `Setup and first steps`              |      [Weblink](https://towardsdatascience.com/space-science-with-python-setup-and-first-steps-1-8551334118f6)       |        [PDF](./doc/tutorials/2_setup_and_first_steps.pdf)        |
|  3   | `A look at Kepler’s first law`       |   [Weblink](https://towardsdatascience.com/space-science-with-python-2-a-look-at-keplers-first-law-84caa6c75a35)    |     [PDF](./doc/tutorials/3_a_look_at_keplers_first_law.pdf)     |
|  4   | `The Solar System centre`            |      [Weblink](https://towardsdatascience.com/space-science-with-python-the-solar-system-centre-6b8ad8d7ea96)       |       [PDF](./doc/tutorials/4_the_solar_system_centre.pdf)       |
|  5   | `The dance of Venus`                 |         [Weblink](https://towardsdatascience.com/space-science-with-python-the-dance-of-venus-926905875afb)         |         [PDF](./doc/tutorials/5_the_dance_of_venus.pdf)          |
|  6   | `Space maps`                         |             [Weblink](https://towardsdatascience.com/space-science-with-python-space-maps-747c7d1eaf7f)             |             [PDF](./doc/tutorials/6_space_maps.pdf)              |
|  7   | `Around the Sun`                     |        [Weblink](https://towardsdatascience.com/space-science-with-python-quite-around-the-sun-6faa206a1210)        |           [PDF](./doc/tutorials/7_around_the_sun.pdf)            |
|  8   | `Comets — Visitors from afar`        |                   [Weblink](https://towardsdatascience.com/comets-visitors-from-afar-4d432cf0f3b)                   |      [PDF](./doc/tutorials/8_comets_visitors_from_afar.pdf)      |
|  9   | `The Origin of Comets`               |        [Weblink](https://towardsdatascience.com/space-science-with-python-the-origin-of-comets-3b2aa57470e7)        |        [PDF](./doc/tutorials/9_the_origin_of_comets.pdf)         |
|  10  | `A Rendezvous with Jupiter`          |     [Weblink](https://towardsdatascience.com/space-science-with-python-a-rendezvous-with-jupiter-55713e4ce340)      |     [PDF](./doc/tutorials/10_a_rendezvous_with_jupiter.pdf)      |
|  11  | `Supplements for Papers`             |       [Weblink](https://towardsdatascience.com/space-science-with-python-supplements-for-papers-4876ec46b418)       |       [PDF](./doc/tutorials/11_supplements_for_papers.pdf)       |
|  12  | `Did we observe everything?`         |     [Weblink](https://towardsdatascience.com/space-science-with-python-did-we-observe-everything-617a8221e750)      |     [PDF](./doc/tutorials/12_did_we_observe_everything.pdf)      |
|  13  | `A comet in 3 D`                     |           [Weblink](https://towardsdatascience.com/space-science-with-python-a-comet-in-3-d-3774b1d71d9b)           |           [PDF](./doc/tutorials/13_a_comet_in_3_d.pdf)           |
|  14  | `Turbulent times of a comet`         |     [Weblink](https://towardsdatascience.com/space-science-with-python-turbulent-times-of-a-comet-7fecedd78169)     |     [PDF](./doc/tutorials/14_turbulent_times_of_a_comet.pdf)     |
|  15  | `An Invisible Visitor`               |        [Weblink](https://towardsdatascience.com/space-science-with-python-an-invisible-visitor-2c8d759509cd)        |        [PDF](./doc/tutorials/15_an_invisible_visitor.pdf)        |
|  16  | `The Solar Orbiter and comet ATLAS`  | [Weblink](https://towardsdatascience.com/space-science-with-python-the-solar-orbiter-and-comet-atlas-8150d66f79aa)  | [PDF](./doc/tutorials/16_the_solar_orbiter_and_comet_atlas.pdf)  |
|  17  | `Bright Dots in the Dark Sky`        |    [Weblink](https://towardsdatascience.com/space-science-with-python-bright-dots-in-the-dark-sky-73909507a0ca)     |    [PDF](./doc/tutorials/17_bright_dots_in_the_dark_sky.pdf)     |
|  18  | `Uncertain Movements of an Asteroid` | [Weblink](https://towardsdatascience.com/space-science-with-python-uncertain-movements-of-an-asteroid-f651b94f7008) | [PDF](./doc/tutorials/18_uncertain_movements_of_an_asteroid.pdf) |
|  19  | `Density Estimators in the Sky`      |   [Weblink](https://towardsdatascience.com/space-science-with-python-density-estimators-in-the-sky-87fbcfb089a6)    |   [PDF](./doc/tutorials/19_density_estimators_in_the_sky.pdf)    |
|  20  | `A very bright Opposition`           |      [Weblink](https://towardsdatascience.com/space-science-with-python-a-very-bright-opposition-62e248abfe62)      |      [PDF](./doc/tutorials/20_a_very_bright_opposition.pdf)      |
|  21  | `Ceres in the Sky`                   |          [Weblink](https://towardsdatascience.com/space-science-with-python-ceres-in-the-sky-fec20fee3f9d)          |          [PDF](./doc/tutorials/21_ceres_in_the_sky.pdf)          |
|  22  | `Asteroid Project (Part 1)`          |      [Weblink](https://towardsdatascience.com/space-science-with-python-asteroid-project-part-1-4fa8809f8bde)       |      [PDF](./doc/tutorials/22_asteroid_project_part_1.pdf)       |
|  23  | `Asteroid Project (Part 2)`          |       [Weblink](https://towardsdatascience.com/asteroid-project-part-2-test-driven-development-ed7af6c1820e)        |      [PDF](./doc/tutorials/23_asteroid_project_part_2.pdf)       |
|  24  | `Asteroid Project (Part 3)`          |      [Weblink](https://towardsdatascience.com/space-science-with-python-asteroid-project-part-3-d7dc0941a717)       |      [PDF](./doc/tutorials/24_asteroid_project_part_3.pdf)       |
|  25  | `Asteroid Project (Part 4)`          |      [Weblink](https://towardsdatascience.com/space-science-with-python-asteroid-project-part-4-ea1361540033)       |      [PDF](./doc/tutorials/25_asteroid_project_part_4.pdf)       |
