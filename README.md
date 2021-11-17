## A pipeline for building wheels for Regions

[![Build Status](https://dev.azure.com/larrybradley/regions-wheel-forge/_apis/build/status/larrybradley.regions-wheel-forge?branchName=master)](https://dev.azure.com/larrybradley/regions-wheel-forge/_build?definitionId=5)

After releasing a new Regions version, update
[autowheel.yml](https://github.com/larrybradley/regions-wheel-forge/blob/master/autowheel.yml)
with the package version, Python versions, and
minimum Numpy version. After pushing the changes, Azure Pipelines will
automatically start to build the wheels.

To manually build the wheels, go to the
[Azure build](https://dev.azure.com/larrybradley/regions-wheel-forge/_build/)
, click on ``larrybradley.regions-wheel-forge``, then click "Run
pipeline", and then click "Run".

Once the builds are complete, download the wheels by running:

    python get_wheels.py

Then upload the wheels to PyPI with `twine`:

    twine upload wheelhouse/*.whl
