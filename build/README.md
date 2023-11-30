## Integration Testing

The different languages clients should all have an integration test suite that is dependent on a dynamic library being present somewhere and a running instance of Flipt. In the `build/` directory we will use [Dagger](https://dagger.io/) to orchestrate setting up the dependencies for running the test suites for the different languages.

### Requirements

Make sure you have `dagger` installed. This module is pinned to `v0.9.3` currently.

Here are the [installation instructions](https://docs.dagger.io/quickstart/729236/cli) for `dagger`.

### How to run tests?

From the root of this repository you can run:

```bash
dagger run go run ./build
```

This will run integration tests for every language that is supported. If you wish to filter specific languages to test, there is a flag `-languages` which accepts a comma-separated list of values.

e.g.

```bash
dagger run go run ./build -languages=python,ruby
```