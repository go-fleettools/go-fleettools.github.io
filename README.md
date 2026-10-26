# go-fleettools.github.io

Landing page of the [go-fleettools](https://github.com/go-fleettools) organisation,
published at <https://go-fleettools.github.io/>. Built with Hugo and the shared design
of [go-fleettools/landingkit](https://github.com/go-fleettools/landingkit), a Hugo
module pinned in `go.mod`.

The brand colours are read from `static/img/logo.svg`
(`go run github.com/go-fleettools/landingkit/cmd/landingkit brand static/img/logo.svg`).
One card per repository is listed in `hugo.toml`, with the latest tag read from the
repository; the `ci` workflow fails if one is missing from the page.

```sh
hugo server
```
