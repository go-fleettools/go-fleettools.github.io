# go-fleettools.github.io

Landing page of the [go-fleettools](https://github.com/go-fleettools) organisation,
published at <https://go-fleettools.github.io/>. Built with Hugo and the shared design
of [go-fleettools/landingkit](https://github.com/go-fleettools/landingkit), a Hugo
module pinned in `go.mod`.

The brand colours are read from `static/img/logo.svg`
(`go run github.com/go-fleettools/landingkit/cmd/landingkit brand static/img/logo.svg`).
One card per repository is listed in `hugo.toml`, with the latest tag read from the
repository; the `ci` workflow fails if one is missing from the page.

Whether those tags are still the latest ones is a different question, asked **daily**
by the `labels` workflow and not on a change: a label goes stale when *another*
repository publishes a tag, so a `push` or `pull_request` trigger would paint a
contributor's branch red for somebody else's release. It is report-only and needs no
secret — `tagcells` reads each latest release with `git ls-remote`. To fix what it
reports:

```sh
tagcells --org go-fleettools --write hugo.toml
```

It is told how many labels this file holds (`min-cells: 11`), because the refusal it
would otherwise make is *"did I read none at all?"*, which stays green while ten of
eleven are read. Removing a repository from the page is one line in that workflow, in
the pull request that removes it.

```sh
hugo server
```
