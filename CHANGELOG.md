# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

## [Unreleased]

### Added
- Python 3.14 support:
  - Added `"Programming Language :: Python :: 3.14"` classifier in `pyproject.toml`.
  - Added support for running and installing on Python 3.14 environments.
- Added `.venv` to `extend-exclude` in `.flake8` to prevent flake8 from scanning virtual environment files.

### Changed
- Updated `requires-python` constraint in `pyproject.toml` from `>=3.9, <3.14` to `>=3.9, <3.15`.
- Updated dependency requirements in `pyproject.toml` using PEP 508 environment markers to support Python 3.14 while maintaining backwards compatibility with Python 3.9–3.13:
  - `scipy`:
    - `scipy>=1.7.3,<1.15; python_version < '3.14'`
    - `scipy>=1.16.1; python_version >= '3.14'` (wheels for Python 3.14 are available from 1.16.1 onwards).
  - `neurokit2`:
    - `neurokit2==0.1.2; python_version < '3.14'`
    - `neurokit2>=0.2.13; python_version >= '3.14'` (resolves removal of `scipy.signal.wavelets.daub` in SciPy 1.15+).
