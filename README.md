# jessepinkman9900.github.io

## Pre-Req
- [pre-commit](https://pre-commit.com/)
- [poetry 1.7.1](https://python-poetry.org/docs/#installation)
- [docker 26.0.0](https://docs.docker.com/get-docker/)

## Misc
1. format code
```shell
poetry run ruff format
```
2. run code checks
```shell
poetry run pre-commit run --all-files
```
3. static type check
```shell
poetry run ruff
```
