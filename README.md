# toml-test action

This action runs [toml-test](https://github.com/BurntSushi/toml-test) with
an encoder or decoder of your choosing.

## Inputs

### `command`

**Required** The shell command to run to invoke your encoder or decoder.

### `encoder`

A Boolean flag specifying whether you are testing an encoder (`true`) or
a decoder (omitted or `false`)

### `run`

A glob pattern to specify which tests to run. Defaults to all.

### `skip`

A glob pattern to specify which tests to skip. Defaults to none.

### `parallel`

Number of tests to run in parallel. Defaults to picking number automatically
based on system characteristics.

### `timeout`

A duration, written as a string (e.g. '2s') for each individual test case.
Defaults to 1 second.

### `test_dir`

A directory path where your custom test cases are located. See the toml-test
repository for more information on custom test cases.

## Example usage

```yaml
uses: g-s-k/toml-test-action@v1.0
with:
  command: python3 src/my-toml-parser.py
  run: 'valid/*/*'
  skip: 'valid/array/*'
```
