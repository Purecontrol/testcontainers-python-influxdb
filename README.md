Brings InfluxDB in testcontainers-python (until [PR #413](https://github.com/testcontainers/testcontainers-python/pull/413) is merged).

# Installation in your project

This package supports versions 1.x and 2.x of InfluxDB.
Specify the version you want to use during the installation so that only the needed Python client library will be installed.

- if you use `pip`:

```sh
# for InfluxDB 1.x versions
pip install testcontainers-python-influxdb[influxdb1]

# for InfluxDB 2.x versions
pip install testcontainers-python-influxdb[influxdb2]

# for both InfluxDB 1.x and 2.x versions (unlikely, but who knows?)
pip install testcontainers-python-influxdb[influxdb1,influxdb2]
```

- if you use `poetry`:

```sh
# for InfluxDB 1.x versions
poetry install testcontainers-python-influxdb[influxdb1]

# for InfluxDB 2.x versions
poetry install testcontainers-python-influxdb[influxdb2]

# for both InfluxDB 1.x and 2.x versions (unlikely, but who knows?)
poetry install testcontainers-python-influxdb[influxdb1,influxdb2]
```

# Tests

- install the libraries for 1.x and 2.x clients:

```sh
poetry install --all-extras
```

- run the automated tests:

```sh
# directly with poetry
poetry run pytest -v
```

Code coverage (with [missed branch statements](https://pytest-cov.readthedocs.io/en/latest/config.html?highlight=--cov-branch)):

```sh
poetry run pytest -v --cov=testcontainers_python_influxdb --cov-branch --cov-report term-missing --cov-fail-under 94
```
## Code conventions

The code conventions are described and enforced by [pre-commit hooks](https://pre-commit.com/hooks.html) to maintain style and quality consistency across the code base.
The hooks are declared in the [.pre-commit-config.yaml](.pre-commit-config.yaml) file.

When you contribute, set the git hooks (pre-commit and commit-msg types) on your development environment:

```sh
poetry run pre-commit install --hook-type pre-commit --hook-type commit-msg
```

Before committing, you can check your changes manually with:

```sh
# put all your changes in the git staging area (or add the changes manually and skip this)
git add -A

# run all hooks
poetry run pre-commit run --all-files

# run a specific hook
poetry run pre-commit run ruff --all-files
```

# Licence

Unless stated otherwise, all works are licensed under the [Apache 2.0](https://spdx.org/licenses/Apache-2.0.html), a copy of which is included [here](LICENSE).
