# Scanning and Parsing ANSI C99

## Module Structure and Sources

```text
.
├── Makefile
├── README.md
├── parser.y
├── scanner.l
└── test
    ├── randerr.c
    └── random.c
```

This module includes the scanner and parser definitions, to accept ANSI C99 syntax. _parser.y_ and _scanner.l_
are adapted from the open-source GitHub Gist: [https://gist.github.com/codebrainz/2933703](https://gist.github.com/codebrainz/2933703).

There are test files in the _test_ directory, to test the scanner and parser.

## Testing

To test the scanner and parser, run the following command:

```bash
make test
```

This will generate the scanner and parser source files and build the `cparser` executable. The executable gets a run on the test files in the _test_ directory.

- The first test file, _random.c_, is a valid C99 program.
- The second test file, _randerr.c_, is an invalid C99 program.

The output of the `make test` command should indicate that the first test file was parsed successfully, and the second test file failed to parse.

Alternatively, you can first build `cparser` by running `make`, and then run the executable on the test files:

```bash
make
# Should succeed
./cparser test/random.c
# Should fail
./cparser test/randerr.c
```

## Notes

The parser is set to exit with a code `0`, regardless whether the source file was a syntactically valid ANSI C99 program or not. The status of the parsing will be indicated by the output of the executable. For a valid program, the output will be `No errors detected.`. For an invalid program, the output will be `Errors detected.`.
