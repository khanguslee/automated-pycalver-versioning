# Automated pycalver Versioning

[![Version 202007.2][version_img]]()

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

5. Edit file patterns in `[pycalver.file_patterns]` inside [pyproject.toml](pyproject.toml)

6. Validate everything was set up correctly

    ```bash
    poetry run pycalver bump --dry
    ```

7. If there's no errors, you can bump versions

   ```bash
   poetry run pycalver bump
   ```

8. See [Github Actions workflow](.github/workflows/main.yml) to automate the process upon push to `master` branch.

[version_img]: https://img.shields.io/static/v1.svg?label=version&message=202007.2&color=blue
