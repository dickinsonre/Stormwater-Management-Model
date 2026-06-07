# Stormwater-Management-Model

Stormwater Management Model (aka "SWMM") solver only

## Introduction
This is the open source SWMM source code repository maintained by the Open
Water Analytics group.

SWMM is a dynamic hydrology-hydraulic water quality simulation model. It is
used for single event or long-term (continuous) simulation of runoff quantity
and quality from primarily urban areas. SWMM source code is written in the C
Programming Language and released under combination a of MIT-License and Public
Domain. For more information on licensing, please see the [LICENSE](https://github.com/OpenWaterAnalytics/Stormwater-Management-Model/blob/develop/LICENSE).

## Project Information

[![license](https://img.shields.io/github/license/mashape/apistatus.svg)](https://github.com/OpenWaterAnalytics/Stormwater-Management-Model/blob/develop/LICENSE)
[![docs](https://img.shields.io/badge/docs-passing-green.svg)](http://wateranalytics.org/Stormwater-Management-Model/)

![build](https://github.com/OpenWaterAnalytics/Stormwater-Management-Model/workflows/Build%20and%20Test/badge.svg?branch=master)

## Citing This Work

Open source software is typically developed by unpaid community-forward volunteers
who see greater purpose for their code bases.  The contributors dedicate much of
their own time to make robust software so that it can be used and easily understood
by users.  When you use any of the compiled or raw code, build scripts, testing
or testing artifacts found in this project consider the amount of time it took
the contributing members to make it.  The following link provides the appropriate
way to cite this software. Show your appreciation through proper citation!

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.5484299.svg)](https://doi.org/10.5281/zenodo.5484299)

## Contributing

Everyone is welcome to contribute to this project.

See [CONTRIBUTING.md](https://github.com/OpenWaterAnalytics/Stormwater-Management-Model/wiki/Contributing) for instructions on setting your development environment.

## OWA-SWMM Testing

To run the test suite for please refer to the [REGRESSION_TESTING.md](https://github.com/OpenWaterAnalytics/Stormwater-Management-Model/wiki/Testing-System)

## Code of Conduct

The SWMM Project follows the [Contributor Covenant Code of Conduct](https://github.com/OpenWaterAnalytics/Stormwater-Management-Model/wiki/Code-of-Conduct)

# Stormwater-Management-Model

A fork of the **Open Water Analytics SWMM solver** repository that contains the open-source computational engine for the Storm Water Management Model, along with build infrastructure, tests, documentation, and release metadata. The repository tracks the `develop` branch of `pyswmm/Stormwater-Management-Model`, is currently up to date with upstream on that branch, and includes 8 branches and 13 tags in this fork.[1]

## Overview

This repository contains the **solver only** implementation of SWMM rather than the full desktop GUI. The current front-page README explicitly identifies it as the “Stormwater Management Model (aka SWMM) solver only,” and describes SWMM as a dynamic hydrology-hydraulic water quality simulation model used for both single-event and continuous simulation of runoff quantity and quality from primarily urban areas.[1]

EPA describes SWMM as software used worldwide for planning, analysis, and design related to stormwater runoff, combined sewers, sanitary sewers, and other drainage systems, while the SWMM 5.2 user manual describes it as a dynamic rainfall-runoff simulation model for runoff quantity and quality from urban areas.[2][3] Taken together, this repository is best understood as the **core engine codebase** for hydraulic and hydrologic simulation, not the user-interface application layer.[1][4]

## What this repository contains

The visible directory structure shows a mature solver project with source, tests, external dependencies, documentation, and CI support.[1]

| Path | Purpose |
|---|---|
| `.github/workflows/` | Continuous integration workflows for build and test automation.[1] |
| `cmake/` | CMake helper modules and build-system logic, including recent changes related to OpenMP placement.[1] |
| `docs/` | Project documentation and versioned documentation support.[1] |
| `extern/` | External code dependencies used by the project, including unit-test support libraries.[1] |
| `src/` | Core SWMM solver source code and toolkit/output API implementation.[1] |
| `tests/` | Regression tests and validation code, including recent fixes for output API date/time handling.[1] |
| `CMakeLists.txt` | Top-level build definition for the solver.[1] |
| `CMakePresets.json` | Shared configure presets for CMake-based builds.[1][5] |
| `CITATION.cff` | Citation metadata for software reuse and scholarly credit.[1] |
| `ReleaseNotes.md` | Historical release notes for earlier code merges and releases.[1] |

GitHub reports the repository language breakdown as **85.2% C**, **14.2% C++**, and **0.6% CMake**, which is consistent with a core computational engine plus test and build infrastructure.[1]

## Scope of the SWMM engine

The repository README says SWMM is a dynamic hydrology-hydraulic water quality simulation model.[1] EPA further describes SWMM as supporting planning, analysis, and design for stormwater runoff, combined and sanitary sewers, and other drainage systems, while the SWMM 5.2 manual explains that it supports both single-event and long-term continuous simulation with multiple file types and result-review workflows.[2][3]

That means this repository is central for developers who want to compile the engine, embed the toolkit in other applications, run automated tests, or work directly with the output API rather than using a graphical modeling interface.[1][6][4]

## Build system and developer workflow

This repository is clearly organized around a **CMake-based** build process. The presence of `CMakeLists.txt`, a `cmake/` folder, CI workflows, and `CMakePresets.json` indicates a modern multi-platform build setup, and CMake documentation confirms that presets are intended to share common configure options across developers and environments.[1][5]

A public `Build.md` file in the USEPA SWMM repository also confirms that the develop branch uses documented build steps for compiling the computational engine.[7] Together with the visible GitHub workflow setup and test directories, this suggests the repository is intended for reproducible local builds, CI validation, and regression testing rather than ad hoc compilation.[1][7]

## Testing and output API work

The visible commit history points to active work on the **output API** and **date/time series functions**. Recent commits in both `src/` and `tests/` mention fixes to `SMO_getDateSeries`, `SMO_getDateTime`, and related error handling.[1]

That matters because OWA-SWMM has documented a toolkit application programming interface for model interaction and output handling, and public announcements note that OWA hosts live toolkit API documentation for version 5.2.0.[6] For developers building wrappers, automation layers, or result-processing tools, this repository is therefore useful not only as a solver but also as a maintained API surface.[1][6]

## Version context

The README visible in this fork was last updated in a commit labeled **Merged in USEPA-SWMM5.2.2**, while the repository tags page shows 13 tags in total.[1] EPA has since published later SWMM releases, including a public 5.2.4 release entry in the USEPA repository releases page.[8]

At the same time, the current `develop` branch in this fork is up to date with `pyswmm/Stormwater-Management-Model:develop`, and the latest visible commit is only four months old.[1] That indicates the branch is still a living development line even though the root README itself is relatively brief and somewhat older.[1]

## Citation and contribution

The repository already includes a `CITATION.cff` file and a DOI link in the README pointing to **10.5281/zenodo.5484299** for software citation.[1] It also points contributors to the project wiki for contributing guidance, testing-system guidance, and a code-of-conduct page based on the Contributor Covenant.[1]

That existing material is useful but could be surfaced more clearly in a stronger README by making development setup, test execution, and branch purpose easier to find from the front page.[1]

## What a more detailed README should add

A stronger README for this fork should explain:

- That this is the **solver-only** SWMM repository, not the GUI application.[1][4]
- What the top-level folders contain and where developers should start.[1]
- How CMake and presets are used to configure builds across platforms.[1][5]
- That the repository includes both solver code and toolkit/output API work, including regression tests.[1][6]
- How this fork relates to upstream `pyswmm/Stormwater-Management-Model` and to official USEPA SWMM releases.[1][8]

## Recommended README draft

Below is a fuller GitHub-facing README draft that could replace or expand the existing one:

***

# Stormwater-Management-Model

`Stormwater-Management-Model` is a fork of the **Open Water Analytics SWMM solver** repository. It contains the open-source computational engine for the Storm Water Management Model (SWMM), together with build infrastructure, tests, documentation, and citation metadata.[1]

## Purpose

This repository provides the **solver-only** codebase for SWMM rather than the desktop graphical user interface. It is intended for developers, researchers, and advanced users who need to compile the engine, inspect or modify source code, work with the toolkit/output API, or validate behavior through automated tests.[1][4]

## About SWMM

SWMM is a dynamic hydrology-hydraulic water quality simulation model used for planning, analysis, and design of stormwater, combined sewer, sanitary sewer, and related drainage systems. It supports both single-event and long-term continuous simulation of runoff quantity and quality from primarily urban areas.[1][2][3]

## Repository contents

- `.github/workflows/` — continuous integration workflows.[1]
- `cmake/` — CMake support files and build modules.[1]
- `docs/` — project documentation.[1]
- `extern/` — external dependencies and test support code.[1]
- `src/` — core solver source and toolkit/output API implementation.[1]
- `tests/` — regression and validation tests.[1]
- `CMakeLists.txt` and `CMakePresets.json` — top-level build configuration.[1]
- `CITATION.cff` — citation metadata.[1]
- `ReleaseNotes.md` — release history notes.[1]

## Development notes

The repository uses a **CMake-based** build workflow and includes shared presets for common configure options.[1][5] Recent commit history shows ongoing work in both the solver and the output API, including fixes for date/time output functions and associated tests.[1]

## Upstream and status

This fork is currently shown as up to date with `pyswmm/Stormwater-Management-Model:develop`.[1] The visible repository metadata shows 8 branches, 13 tags, and 1,740 commits in the develop branch history.[1]

## Citation

When using this code in research, publications, or derivative tools, use the DOI linked in the repository README: [10.5281/zenodo.5484299](https://doi.org/10.5281/zenodo.5484299).[1]

## Related references

- [EPA SWMM overview](https://www.epa.gov/water-research/storm-water-management-model-swmm) [2]
- [SWMM 5.2 User’s Manual](https://www.epa.gov/system/files/documents/2022-04/swmm-users-manual-version-5.2.pdf) [3]
- [USEPA build notes](https://github.com/USEPA/Stormwater-Management-Model/blob/develop/Build.md) [7]
- [USEPA releases](https://github.com/USEPA/Stormwater-Management-Model/releases) [8]

***
