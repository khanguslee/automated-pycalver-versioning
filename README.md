# Automated pycalver Versioning

[![Version 202007.1][version_img]]()
Spike program to work out how to get pycalver to automatically version files with every master branch commit.

## Setting Up

Instructions on how to setup from scratch.

1. Install [`poetry`](https://python-poetry.org/docs/)
2. Set up project with poetry and follow instructions

    ```bash
    poetry init
    ```

3. Install [`pycalver`](https://gitlab.com/mbarkhau/pycalver) library

    ``` bash
    poetry add --dev pycalver
    ```

4. Initialise `pycalver`

    ```bash
    poetry run pycalver init
    ```

[version_img]: https://img.shields.io/static/v1.svg?label=version&message=202007.1&color=blue
