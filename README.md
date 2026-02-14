# Error Classification

[![GoDoc](https://pkg.go.dev/badge/github.com/bassosimone/errclass)](https://pkg.go.dev/github.com/bassosimone/errclass) [![Build Status](https://github.com/bassosimone/errclass/actions/workflows/go.yml/badge.svg)](https://github.com/bassosimone/errclass/actions) [![codecov](https://codecov.io/gh/bassosimone/errclass/branch/main/graph/badge.svg)](https://codecov.io/gh/bassosimone/errclass)

The `errclass` Go package classifies Go errors into an enum of strings
with names resembling standard Unix error names (e.g., `ETIMEDOUT`,
`ECONNRESET`, `EDNS_NONAME`). This is useful for structured logging
and systematic analysis of network errors.

For example:

```Go
import "github.com/bassosimone/errclass"

// Classify any error into a Unix-like error name.
class := errclass.New(err)

// The result is a string like "ETIMEDOUT", "ECONNRESET",
// "EDNS_NONAME", "ETLS_CA_UNKNOWN", or "" for nil errors.
log.Printf("error: %s, class: %s", err, class)
```

## Installation

To add this package as a dependency to your module:

```sh
go get github.com/bassosimone/errclass
```

## Development

To run the tests:
```sh
go test -v .
```

To measure test coverage:
```sh
go test -v -cover .
```

## License

```
SPDX-License-Identifier: GPL-3.0-or-later
```

## History

Adapted from [rbmk-project/rbmk](https://github.com/rbmk-project/rbmk/tree/v0.17.0/pkg/common/errclass/).
