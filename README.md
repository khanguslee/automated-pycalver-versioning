# Automated pycalver Versioning

[![Version 202007.2][version_img]]()

Spike program to work out how to get pycalver to automatically version files with every master branch commit.

**tldr: A fully automated pycalver versioning system only works if the branch you are in is _not protected_.**

## Setting Up

Instructions on how to setup from scratch.

1. Install [`poetry`](https://python-poetry.org/docs/)
2. Set up project with poetry and follow instructions

   ```bash
   poetry init
   ```

3. Install [`pycalver`](https://gitlab.com/mbarkhau/pycalver) library

   ```bash
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

## What does pycalver do?

The following steps occur when you run `pycalver bump`, as mentioned in the [pycalver readme](https://gitlab.com/mbarkhau/pycalver#bump-it-up)

> 0. _Check_ that your repo doesn't have any local changes.
> 1. _Fetch_ the most recent global VCS tags from origin (-n/--no-fetch to disable).
> 2. _Generate_ a new version, incremented from the current version.
> 3. _Update_ version strings in all files configured in file_patterns.
> 4. _Commit_ the updated version strings.
> 5. _Tag_ the new commit.
> 6. _Push_ the new commit and tag.

`pycalver` uses the largest git tag that matches the `version_pattern` stated in your config file. Mentioned in the readme [here](https://gitlab.com/mbarkhau/pycalver#bump-it-up).

## Conclusion

You can automate pycalver version bumping if the branch you want to commit on (usually `master` branch) is not a protected branch.

If your branch _is_ protected, you can still tag your branch with the new version number and push it using `pycalver`. However, if you want to commit related file changes that edit version number strings, you cannot do this automatically.

[version_img]: https://img.shields.io/static/v1.svg?label=version&message=202007.2&color=blue
