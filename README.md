# isomorphic-test (WORK IN PROGRESS)
Write isomorphic tests for your isomorphic library

This tool is designed to make writing plugins for isomorphic-git easier.
It consists of all the hacks I used to write isomorphic-git's own unit tests.
I extracted all the hackery and bundled it into this command line tool.

# Writing tests

Tests are written in Jasmine, because it works in the browser.

## Features

### File fixtures

Tests can 'require' file system fixtures using FixtureFS().
Place each fixture into a separate directory by name, inside the '__tests__/__fixtures__' directory.
### Git repo fixtures

The test runner starts its own git server.
Any directories in '__tests__/__gitrepos__' will be served as git fixtures.

### Snapshot fixtures

Jest-style snapshots are saved in '__tests__/__snapshots__'.
They must be loaded manually however, using 'registerSnapshots'.

### Server response mocking

The 'nockback' library allows you to capture and replay HTTP responses delivered to your tests.
Get rid of those slow flaky "real" http requests and enjoy fast, predictable responses to your requests.
Nockback fixtures go in the '__tests__/__nockbacks__' directory.
