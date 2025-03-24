# ktfmt-pre-commit-hook
A [pre-commit](https://pre-commit.com/) hook to run [ktfmt](https://github.com/facebookincubator/ktfmt).

## Requirements

This commit hook requires Python `>=3.8`.

`ktfmt` requires Java 11. The `java` in your `PATH` must be version `>=11`.

## Usage Instructions

Add the following lines to your `.pre-commit-config.yaml`.

```yaml
- repo: https://github.com/shonk-software/ktfmt-pre-commit-hook
  rev: 0.8.0
  hooks:
  - id: ktfmt
    stages: [commit]
```

We use it with the following options:
```yaml
- repo: https://github.com/corewar-teamprojekt/ktfmt-pre-commit-hook
  rev: 0.8.0
  hooks:
  - id: ktfmt
    args: [--dry-run, --kotlinlang-style]
```

With `--dry-run` the hook doesn't automatically format the files on commit.  
With `--kotlinlang-style` the hook uses 4-space indentation instead of 2-space indentation.  

See the [ktfmt documentation](https://facebookincubator.github.io/ktfmt/) for supported command line arguments.

Please report any bugs in the [issue tracker](https://github.com/davehadley/ktfmt-pre-commit-hook/issues).

## Development Instructions

### Environment Setup

Run `source setup.sh` to setup the development environment.
This may be slow the first time that this is run as the virtual environment is created
and dependencies are installed.

### Testing

Run:

```
poetry install
poetry run pytest tests
```

## License

Licensed under either of

 * Apache License, Version 2.0
   ([LICENSE-APACHE](LICENSE-APACHE) or http://www.apache.org/licenses/LICENSE-2.0)
 * MIT license
   ([LICENSE-MIT](LICENSE-MIT) or http://opensource.org/licenses/MIT)

at your option.

### Contribution

Unless you explicitly state otherwise, any contribution intentionally submitted for inclusion in the work by you, as defined in the Apache-2.0 license, shall be dual licensed as above, without any additional terms or conditions.
