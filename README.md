# blktests

blktests is a test framework for the Linux kernel block layer and storage
stack. It is inspired by the [xfstests](https://git.kernel.org/pub/scm/fs/xfs/xfstests-dev.git/)
filesystem testing framework.

## Getting Started

The dependencies are minimal, but make sure you have them installed:

- bash
- GNU coreutils
- util-linux
- fio

Add the list of block devices you want to test on in a file named `config`:

```sh
TEST_DEVS=(/dev/nvme0n1 /dev/sdb)
```

And as root, run the default set of tests with `./check`.

Note that these tests are destructive, so don't add anything to the `TEST_DEVS`
array containing data that you want to keep.

[Documentation/running-tests.md] has more detailed information on configuration
and running tests.

## Adding Tests

The `./new` script creates a new test from a template.
[Documentation/writing-tests.md] has more information on how to write a test.
