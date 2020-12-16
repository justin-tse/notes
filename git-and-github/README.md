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
git reset --hard origin/master
```