> _Wahoo_: The Fishshell Framework

![](https://img.shields.io/badge/100% -Fresh-00cc00.svg?style=flat-square)
![](https://img.shields.io/badge/Wahoo-Framework-00b0ff.svg?style=flat-square)
![](https://img.shields.io/badge/Mac-OSX-FF0066.svg?style=flat-square)
![](https://img.shields.io/badge/Linux-Common-FF0066.svg?style=flat-square)
![](https://img.shields.io/badge/License-MIT-707070.svg?style=flat-square)

<a name="wahoo"></a>

<br>

<p align="center">
<a href="https://github.com/bucaran/wahoo/blob/master/README.md">
<img width="40%" src="https://cloud.githubusercontent.com/assets/8317250/7772540/c6929db6-00d9-11e5-86bc-4f65533243e9.png">
</a>
</p>

<br>

<p align="center">
<b><a href="#about">About</a></b>
|
<b><a href="#install">Install</a></b>
|
<b><a href="#usage">Usage</a></b>
|
<b><a href="#contributing">Contributing</a></b>
|
<b><a href="DOC.md">Documentation</a></b>

</p>

<br>

# About [![][TravisLogo]][Travis]

_Wahoo_ is an all-purpose framework and decentralized package manager for the [fishshell][Fishshell]. It looks after your configuration, themes and plugins. It's light, fast and easy to use.


# Install
> Requires `sudo` to install [fish][Fishshell] and other [dependencies](#deps).

```sh
curl -L git.io/wa | sh
wa help
```

### About `sudo`

You don't need to use `sudo` if you already have `fish` installed or can use [Homebrew](http://brew.sh/), but if you are starting from scratch you need to `sudo` in order to install `fish`, its dependencies and modify the system's default shell.

# Usage

> Each command is preceded by `wa`, e.g, `wa help`

## `update`

Update the framework using [`git`][git].

Updates are not destructive. Unstaged changes are [stashed](https://git-scm.com/book/no-nb/v1/Git-Tools-Stashing) and reapplied after pulling updates from upstream. Similarly, if you have committed changes to the repo they are [rebased](https://git-scm.com/book/en/v2/Git-Branching-Rebasing) with master.

## `get <theme/package>`

Install one or more themes or packages. Discover packages with `wa get` _without_ arguments or themes with `wa themes`. If the package is already installed it will be updated to the latest version.

## `list`

List all packages in the registry. Same as `wa get` _without_ arguments.

## `use <theme>`

Apply a theme. If the theme is not installed, it will be from the registry. To list all the installed themes type `wa use` _without_ arguments.

## `remove <theme/package>`

Remove a theme or package. Packages listening to `uninstall` events will be called before the package is removed from disk to allow custom cleanup of resources, etc. See [Documentation](DOC.md#uninstall).


## `submit <theme/package>`

> Current directory must be under `git` source control and have a remote origin.

Creates a new branch `add-<theme/package name>` in your local fork of Wahoo and adds a new entry to the local registry under `$WAHOO_PATH/db` using the [`$PWD`](http://en.wikipedia.org/wiki/Working_directory)'s git remote origin. If you haven't forked Wahoo, this also forks the project on GitHub and updates your local clone remote [origin](http://stackoverflow.com/questions/9529497/what-is-origin-in-git) and [upstream](http://stackoverflow.com/questions/2739376/definition-of-downstream-and-upstream).

Finally, the GitHub's repository is launched in your preferred browser. You can submit a PR from there.

If you prefer to roll your own, simply add a new file `<package name>.pkg` or `<theme name>.theme` with the remote URL into `$WAHOO_PATH/db` and submit a new PR. See [Documentation](DOC.md#submitting-a-package).


## `help`

Show Wahoo's help on the terminal.

## `version`

Display version.

# Dependencies

[![](https://img.shields.io/badge/Fish-Shell-fb0044.svg?style=flat-square)
][Fishshell]
[![](https://img.shields.io/badge/git-scm-ff8f00.svg?style=flat-square)] [git]

# Contributing

[Fork](https://github.com/bucaran/wahoo/fork) the repo, _clone your own copy_ and start using Wahoo to handle your fish configuration. If you think something is missing, make a theme or find a bug, consider creating a PR.

Consult the [documentation](DOC.md) to learn how to create packages.

# License

[MIT](http://opensource.org/licenses/MIT) © [Jorge Bucaran][Author] et [al](https://github.com/bucaran/wahoo/graphs/contributors)

[Author]: http://about.bucaran.me
[TravisLogo]: http://img.shields.io/travis/bucaran/wahoo.svg?style=flat-square
[Travis]: https://travis-ci.org/bucaran/wahoo
[Fishshell]: http://fishshell.com
[git]: http://git-scm.com/

