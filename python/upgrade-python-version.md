## Upgrade Python version with `pyenv`

Uninstall `pipx`

```sh
python -m pip uninstall pipx
```

Update pyenv and install python version

```sh
pyenv update

pyenv install MAJOR.MINOR.PATCH
```

Use the newly installed version

```sh
pyenv global MAJOR.MINOR.PATCH
```

Upgrade toolchain and install tools again

```sh
python -m pip install --upgrade pip setuptools

python -m pip install --user pipx
```

Reinstall packages with `pipx`

```sh
pipx reinstall-all
```

Note: This *should* just work™ but it *may* not. In that case, google is your friend and if it's not, you may have to roll back.

## Optional

Uninstall the old python version

```sh
pyenv uninstall MAJOR.MINOR.PATCH
```

Update pipenv venvs

```sh
# From directory with `Pipfile`
pipenv --rm

pipenv install --dev
```

Note: You may need to update the `python_version` directive in your `Pipfile`.
