# My Error: Git and Github 
## 2020.12
### Day16: git push error
```zsh
(base)  XF@MacBook-Pro ⮀ ~/src/justin-tse/theodinproject/01-ruby-programming ⮀ ⭠ master± ⮀ git status
On branch master
Your branch and 'origin/master' have diverged,
and have 1 and 1 different commits each, respectively.
  (use "git pull" to merge the remote branch into yours)

All conflicts fixed but you are still merging.
  (use "git commit" to conclude merge)

Untracked files:
```
```zsh
(base)  ✘ XF@MacBook-Pro ⮀ ~/src/justin-tse/theodinproject/01-ruby-programming ⮀ ⭠ master± ⮀ git push origin master
To github.com:justin-tse/theodinproject.git
 ! [rejected]        master -> master (non-fast-forward)
error: failed to push some refs to 'git@github.com:justin-tse/theodinproject.git'
hint: Updates were rejected because the tip of your current branch is behind
hint: its remote counterpart. Integrate the remote changes (e.g.
hint: 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
```
- [Solution](https://stackoverflow.com/questions/19864934/git-your-branch-and-origin-master-have-diverged-how-to-throw-away-local-com)
```zsh
git fetch origin
git reset --hard origin/main     or (master)
```


## 2021.01.27 git push large file warning
- 1. more than 50 Mb will be warning
- 2. more than 100 Mb will be error
- Solution
https://git-lfs.github.com/

1. Initial first time install
Homebrew: brew install git-lfs
MacPorts: port install git-lfs

2. First time using
```shell
git lfs install
```

3. Use Git LFS to select the file types in your respository
```shell
git lfs track "*.psd"
```
means all .psd files in your respository

If you want to track every respository
[source][https://git-scm.com/docs/gitattributes]

make sure .gitattributes is tracked
```shell
git add .gitattributes
```
4. Just commit and push to GitHub as you normally would; for instance, if your current branch is named main:
```shell
git add file.psd
git commit -m "Add design file"
git push origin main
```

## 20210210  brew update error
- Problem
```bash
(base)  ✘ XF@MacBook-Pro ⮀ ~/src/justin-tse/notes/edX/cs50t ⮀ ⭠ main± ⮀ brew update
Error: 
  homebrew-core is a shallow clone.
  homebrew-cask is a shallow clone.
To `brew update`, first run:
  git -C /usr/local/Homebrew/Library/Taps/homebrew/homebrew-core fetch --unshallow
  git -C /usr/local/Homebrew/Library/Taps/homebrew/homebrew-cask fetch --unshallow
This restriction has been made on GitHub's request because updating shallow
clones is an extremely expensive operation due to the tree layout and traffic of
Homebrew/homebrew-core and Homebrew/homebrew-cask. We don't do this for you
automatically to avoid repeatedly performing an expensive unshallow operation in
CI systems (which should instead be fixed to not use shallow clones). Sorry for
the inconvenience!
```
- Solution

```bash
(base)  ✘ XF@MacBook-Pro ⮀ ~/src/justin-tse/notes/edX/cs50t ⮀ ⭠ main± ⮀ git -C /usr/local/Homebrew/Library/Taps/homebrew/homebrew-core fetch --unshallow
remote: Enumerating objects: 359301, done.
remote: Counting objects: 100% (359280/359280), done.
remote: Compressing objects: 100% (145246/145246), done.
remote: Total 350789 (delta 208113), reused 345248 (delta 202741), pack-reused 0
Receiving objects: 100% (350789/350789), 94.61 MiB | 57.00 KiB/s, done.
Resolving deltas: 100% (208113/208113), completed with 7864 local objects.
From https://github.com/Homebrew/homebrew-core
   c1b738be8f..0e1ceaf36e  master     -> origin/master
(base)  XF@MacBook-Pro ⮀ ~/src/justin-tse/notes/edX/cs50t ⮀ ⭠ main± ⮀ git -C /usr/local/Homebrew/Library/Taps/homebrew/homebrew-cask fetch --unshallow
remote: Enumerating objects: 54072, done.
remote: Counting objects: 100% (51588/51588), done.
remote: Compressing objects: 100% (15813/15813), done.
remote: Total 45634 (delta 33305), reused 42067 (delta 29805), pack-reused 0
Receiving objects: 100% (45634/45634), 19.19 MiB | 31.00 KiB/s, done.
Resolving deltas: 100% (33305/33305), completed with 3453 local objects.
From https://github.com/Homebrew/homebrew-cask
   d66341771c..332906e385  master     -> origin/master
```
