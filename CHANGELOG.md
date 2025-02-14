# Changelog

All notable changes to `libcasm-clexulator` will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added

- Added `libcasm.clexulator.PrimNeighborList.weight_matrix()` to access the weight matrix


## [2.0a4] - 2024-03-14

### Fixed

- Fixed DoFSpace basis pseudoinverse calculation

### Added

- Added gradients of correlations functionality in C++, Python functions
- Added FADBAD library to support compiling of Clexulators capable of calculating gradients 
- Added methods to libcasm.clexulator.PrimNeighborList to construct a PrimNeighborList with default parameters for a libcasm.xtal.Prim and to expand and access the neighbors.
- Added libcasm.clexulator.make_default_prim_neighbor_list
- Added methods to libcasm.clexulator.SuperNeighborList to access the neighbor sites and unitcells.
- Added support in ConfigDoFValues for multiple discrete DoF
- Added CASM::clexulator::get_dof_vector_value_at and CASM::clexulator::get_mean_dof_vector_value


### Changed

- Updated docs for PyData Sphinx Theme 0.14.3, particularly dark theme colors and logo
- Changed "intensive_value" methods to "per_unitcell" and "extensive_value" methods to "per_supercell"
- Changed names of libcasm.clexulator.PrimNeighborList methods default_nlist_weight_matrix to default_lattice_weight_matrix and default_nlist_sublattice_indices to default_sublattice_indices

### Removed

- Removed libcasm.clexulator.PrimNeighborList.default_nlist


## [2.0a3] - 2023-10-25

### Fixed

- Fixed error messages for conversion of local DoF to the standard basis
- Fixed DiffClexParamPack traits namespace
- Fixed DoFSpace.is_global binding

### Added

- Tests for correct treatment of local DoF basis with dim=0 on some sublattices


## [2.0a2] - 2023-09-28

### Fixed

- Fixed calculation of homogeneous mode space when some sites do not include a local DoF


## [2.0a1] - 2023-08-20

This release separates out casm/clexulator from CASM v1. It creates a Python package, libcasm.clexulator, that enables using casm/clexulator and may be installed via pip install, using scikit-build, CMake, and pybind11. This release also includes usage and API documentation for using libcasm.clexulator, built using Sphinx.

### Added

- Added Python package libcasm.clexulator
- Added scikit-build, CMake, and pybind11 build process
- Added GitHub Actions for unit testing
- Added GitHub Action build_wheels.yml for Python x86_64 wheel building using cibuildwheel
- Added Cirrus-CI .cirrus.yml for Python aarch64 and arm64 wheel building using cibuildwheel
- Added Python documentation

### Removed

- Removed autotools build process
- Removed boost dependencies
