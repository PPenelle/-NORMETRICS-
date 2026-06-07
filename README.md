# Normetrics Core
NORMETRICS IS A NEW COMMERCIAL SOFTWARE PACKAGED INTO AN API AVAILABLE FOR DEMO AND EVALUATION UNDER NON-DISCLOSURE AGREEMENT. A FULL SUITE OF TESTS INCLUDING BENCHMARKING NORMETRICS PERFORMACE AGAINST INDUSTRY STANDARDS FOR OLS, GLS, 2SLS IS AVAILABLE. CONTACT ppenelle@icloud.com IF INTERESTED IN LICENSING THE TECHNOLOGY. THE CURRENT SCOPE OF NORMETRICS IS:

ALL MULTIVARIATE LINEAR NORM-BASED ECONOMETRIC MODELS, REGULARIZED OR NOT.

NORMETRIC'S novel technology gives users access to estimating any such model mathematically well-defined, without being limited by the number of those pre-coded in the API since NORMETRIC disposes altogether of pre-coded models and estimators.Users simply call NORMETRICS' API with the same call-signature without regard to the model and estimator selected, and indicate in the call the familiy of model they are looking for. NORMETRICS takes care of validating the data, the inputs submitted (kwargs) for the specific family requested, and guarantees the existence of a solution for all models within NORMETRICSS' current scope (linear norm-based models).

NORMETRICS' TECHNOLOGY ELIMINATES THE USE (AND LIMITATIONS) OF PRE-CODED MODELS FROM ITS API, GIVING USERS MUCH INCREASED FLEXIBITY IN ESTIMATING STANDARD AND NON-STANDARD MODELS NOT NATIVELY AVAILABLE IN TRADITIONAL SOFTWARE AND APIS, INCLUDING THE CHOICE OF SOLVER USED.

## Overview

Normetrics is a generalized econometric estimation engine designed around a new technology eliminating the use in its API of pre-coded models and estimators. Users are no longer constraints to models and estimators pre-coded in their favorite econometrics or machine learnings software package or API. Users can choose the solver they want to use or use Normetric's optimal choice of a solver.  It reproduces benchmarked classical estimators outputs under aligned specifications and documented numerical tolerances. Benchmarking test results for OLS, GLS, 2SLS are provided herein. Full demos of Normetrics capabilities can be arranged.

The current validation program focuses on empirical estimator reproduction rather than disclosure of proprietary internal construction logic. For the estimator families that have been explicitly benchmarked, Normetrics is validated against accepted external reference implementations.

A packaged benchmarking test suite will be made available under NDA for companies interested in licensing the technology. See ##2 below for more infomrmation.

## Current Benchmark Coverage

External benchmark parity has currently been established for:

- OLS
- GLS
- 2SLS / IV

These benchmark families are currently validated against trusted Python reference implementations under aligned specifications and documented numerical tolerances.

## Validation Approach

Normetrics uses a two-layer validation structure:

### 1. Fast correctness / regression suite

This layer validates the internal stability of the framework, including:

- data-shape validation
- matrix and invertibility checks
- supported loss formulations
- supported regularization formulations
- model fit-path stability
- selected internal metric consistency checks
- scanner behavior

### 2. External benchmark suite

This layer validates estimator parity against external references:

- OLS benchmarked against statsmodels.OLS
- GLS benchmarked against transformed-system references and statsmodels.GLS
- 2SLS / IV benchmarked against a closed-form projection estimator and linearmodels.IV2SLS

The benchmark objective is straightforward:

For benchmarked estimator families, does Normetrics reproduce accepted reference outputs under aligned specifications within documented numerical tolerances?

## Installation

Create and activate a Python virtual environment, then install the package and test dependencies as needed.

### Core test setup

python -m pip install pytest
python -m pip install -e .

### Benchmark dependencies

python -m pip install -r requirements-benchmarks.txt

The benchmark dependency file currently includes:

statsmodels
linearmodels

## Running the Test Suite

### Run the full suite

python -m pytest tests -q

### Run the full suite with verbose output

python -m pytest tests -vv

### Run benchmark tests only

python -m pytest tests\benchmarks -vv

### Run estimator benchmarks individually

python -m pytest tests\benchmarks\test_ols_reference.py -vv
python -m pytest tests\benchmarks\test_gls_reference.py -vv
python -m pytest tests\benchmarks\test_iv_reference.py -vv

## Interpreting Results

A passing fast test suite indicates that the internal numerical and validation contracts of the framework remain intact.

A passing benchmark suite indicates that, for the estimator families currently benchmarked, Normetrics reproduces accepted external reference outputs under aligned specifications within documented numerical tolerances.

Current benchmarked estimator families:

- OLS
- GLS
- 2SLS / IV

## Scope and Boundaries

The current benchmark program supports explicit claims for the estimator families listed above.

It should not yet be interpreted as a blanket claim that every possible future estimator family or every possible supported configuration has already been externally benchmarked.

The benchmark suite is designed to support reproducible empirical validation of the currently benchmarked estimator families, not to disclose proprietary implementation details.

## Licensing / Technical Evaluation Note

Normetrics is intended to be evaluated primarily through empirical benchmark parity rather than publication of proprietary internal estimation-construction logic.

For technical evaluation, the key diligence question is:

Does Normetrics reproduce accepted estimator outputs accurately, reproducibly, and under a benchmark protocol that can be re-run?

The current benchmark suite is designed to answer that question directly for OLS, GLS, and 2SLS.

## Repository Contents

- tests/ — fast correctness and regression tests
- tests/benchmarks/ — external reference benchmark suite
- requirements-benchmarks.txt — benchmark dependency list

## Status

Normetrics currently has benchmark parity established for:

- OLS
- GLS
- 2SLS / IV

under aligned specifications and documented numerical tolerances.
``
