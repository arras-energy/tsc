# Release 4.3.17

| Title  | Status Report
| ------ | -------------
| Date   | 6 August 2026
| Author | David P. Chassin

See https://github.com/arras-energy/gridlabd/pull/358 for details.

## Fixes
- `raw2glm` converter errors fixed for PSS/E to GLM.
- `pypower` module units for generation startup and shutdown costs changed from `$/MW` to `$`.
- MacOS setup script issues with changes to required libraries

## Additions

- `mapping` network plotting tools using map and mapbox.
- `forecast` weather mapping tool.
- `county` field added to `pypower/powerplant` object.
- `pypower` branch and bus dual variable mapping added.
- `project` subcommand to create and manage gridlabd projects on github.
- `dcline` object added to `pypower` module.
- `zipload` object added to `powerflow` module.
- Files required by LF Energy (`CODE_OF_CONDUCT`, `CONTRIBUTING`, `COMMITTERS`, `SUPPORT`, and `GOVERNANCE`)
- `noaa_weather` tool added
- MacOS 26 support

## Deprecations

None

## Deletions

- Support for MacOS 13.

## Build

- Github actions workflow for `pylint` analysis.
- C++ code analysis using `cppcheck`.

## Validation

- Disabled `ISONE` tool test because the test data is no longer available from ISONE.
- Disabled `noaa_weather` test on github because the memory required exceeds what github actions provides by default.

## Documentation

- `SINGULARITY.md` to document how to run `gridlabd` in singularity environment.

# Recommendations

- [ ] Change release numbering schema to use the release year for the major number and the sequence number for the minor number, e.g., `26.1.1-260804`. The patch number and build id schemas remain the same, i.e., sequential and based on build date, respectively. This would conform more to what many other applications are doing now. This would also eliminate confusion with PNNL's release numbering which is similar but with orthogonal capabilities. This will be done starting with the next release in Fall 2026. (Approved by TSC 8/10/25)

- [ ] Begin an effort to split the `gridlabd` repository into separate repositories that are installed only as required, e.g.,
    - `arras`: the main C/C++ simulation engine
    - `cloud`: support websites
    - `converters`: model and data converters
    - `geodata`: GIS support
    - `module-*`: gridlabd modules
    - `python`: python environment
    - `subcommands`: subcommands
    - `tools`: tools
  The main benefit of this approach is to speed up build, install, and validation performance and simplify maintenance of the entire Arras ecosystem. (Approved by TSC 8/10/25)

- [ ] Stop using the `develop` branch to collect updates to `master` branch and make all pull requests directly to `master`. This should reduce by more than 50% the number of build/validate actions on github. (Approved by TSC 8/10/25)

- [ ] Prioritize open issues using urgent/high/medium/low.  (Approved by TSC 8/10/25)
