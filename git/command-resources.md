# git

----
## table of contents

- [override author for next commits](#override-author-for-next-commits)
- [amend author of last commit](#amend-author-of-last-commit)
- [amend-author-from-root](#amend-author-from-root)
- [resources](#resources)

----


### override author for next commits
```shell
git commit --author="ShivakumarSwamy <shivakumarswamy.bg@gmail.com>"
```

### amend author of last commit
```shell
git commit --amend --author="ShivakumarSwamy <shivakumarswamy.bg@gmail.com>"
```

### amend author from root

1. rebase from root: `git rebase --interactive --root`

2. pick the commit(s) to edit

3. edit author of that specific commit: `git commit --amend --author="ShivakumarSwamy <shivakumarswamy.bg@gmail.com>"` 

4. continue rebase: `git rebase --continue`

5. repeat 3 & 4 n times until all the commits are edited

### resources
- [how can i change the author name / email of a commit?](https://www.git-tower.com/learn/git/faq/change-author-name-email/)