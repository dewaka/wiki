# Git

## Tools

- [Magit - A Git Porcelain inside Emacs](https://magit.vc) - this is probably
  the best git tool to quickly get work done if you are already married to the
  Emacs ecosystem.

## Tips

- Undoing a `git add` before commit -
  <https://stackoverflow.com/questions/348170/how-do-i-undo-git-add-before-commit>.
- Removing untracked files -
  <https://koukia.ca/how-to-remove-local-untracked-files-from-the-current-git-branch-571c6ce9b6b1>
  
  - `git clean -n` - to check which files will be deleted.
  - `git clean -f` - to delete untracked files.
- Rebase remote master - <https://stackoverflow.com/questions/7929369/how-to-rebase-local-branch-with-remote-master/18442755>,
  ```sh
  git fetch origin            # Updates origin/master
  git rebase origin/master    # Rebases current branch onto origin/master
  ```

  This can be done in one step - `git pull --rebase origin master`
- Undoing a git rebase - <https://stackoverflow.com/questions/134882/undoing-a-git-rebase>.
