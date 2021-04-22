## 01. ls --help error
```shell
(base)  ✘ XF@MacBook-Pro ⮀ ~/src/justin-tse/front-end/outline ⮀ ⭠ main± ⮀ ls --help
ls: illegal option -- -
usage: ls [-@ABCFGHLOPRSTUWabcdefghiklmnopqrstuwx1%] [file ...]
```
Solution:
[ls: illegal option -- - #966
](https://github.com/sorin-ionescu/prezto/issues/966)


>brew install coreutils
export PATH="/usr/local/opt/coreutils/libexec/gnubin:$PATH"


```
(base)  ✘ XF@MacBook-Pro ⮀ ~/src/justin-tse/front-end/outline ⮀ ⭠ main± ⮀ brew install coreutils

Updating Homebrew...
==> Auto-updated Homebrew!
Updated 1 tap (homebrew/core).
==> New Formulae
macchina                                                                       mr2
==> Updated Formulae
Updated 57 formulae.

==> Downloading https://ghcr.io/v2/homebrew/core/coreutils/manifests/8.32-2
######################################################################## 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/coreutils/blobs/sha256:371ec57703b3646e0113331308b6e03617c2a7f91e15e113380b605455daba20
==> Downloading from https://pkg-containers-az.githubusercontent.com/ghcr1/blobs/sha256:371ec57703b3646e0113331308b6e03617c2a7f91e15e113380b605455daba20?se=
######################################################################## 100.0%
Error: coreutils 8.31 is already installed
To upgrade to 8.32, run:
  brew upgrade coreutils
(base)  ✘ XF@MacBook-Pro ⮀ ~/src/justin-tse/front-end/outline ⮀ ⭠ main± ⮀ export PATH="/usr/local/opt/coreutils/libexec/gnubin:$PATH"
```

These work for me.

