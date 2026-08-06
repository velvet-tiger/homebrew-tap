# velvet-tiger/homebrew-tap

Homebrew tap for velvet-tiger tools.

## Install

```bash
brew install velvet-tiger/tap/portly
```

Homebrew adds the tap on first use, so there is no separate `brew tap` step.

To remove the tap and everything installed from it:

```bash
brew uninstall portly
brew untap velvet-tiger/tap
```

## Available

| Cask | What it does |
|---|---|
| [portly](https://github.com/velvet-tiger/portly) | Finds the development servers running on your machine |

## The repository name is load-bearing

This repository must stay named `homebrew-tap`. Homebrew resolves `velvet-tiger/tap/portly` by stripping the `homebrew-` prefix and looking for the rest. Rename it and `brew install velvet-tiger/tap/portly` stops resolving.

## Do not edit the casks by hand

Everything in `Casks/` is generated. Each source repository runs GoReleaser on a tag push, which writes the cask here with the release URLs and their checksums. A hand edit is overwritten by the next release, and a hand-written checksum that does not match the published archive makes `brew install` fail for everyone.

To change what a cask contains, change the `homebrew_casks` block in that tool's `.goreleaser.yaml` and cut a new tag.

## Access

Releases push here using a fine-grained token held as a secret in each source repository. The token needs `contents: write` on this repository and nothing else. A repository's own `GITHUB_TOKEN` cannot write across repositories, which is why a separate token exists.
