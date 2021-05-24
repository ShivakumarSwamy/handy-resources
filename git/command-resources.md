# git

----
## table of contents

- [table of contents](#table-of-contents)
- [commit](#commit)
    * [author](#author)
        + [override author for next commits](#override-author-for-next-commits)
        + [amend author of last commit](#amend-author-of-last-commit)
        + [amend author from root](#amend-author-from-root)
    * [sign](#sign)
        + [amend and sign commit with not edit](#amend-and-sign-commit-with-not-edit)
    * [config](#config)
        + [set locally gpg program](#set-locally-gpg-program)
        + [set locally gpg sign](#set-locally-gpg-sign)
        + [set locally gpg signing key id](#set-locally-gpg-signing-key-id)
        + [set locally user name](#set-locally-user-name)
        + [set locally email](#set-locally-email)
- [resources](#resources)

----

## commit

### author

#### override author for next commits
```shell
git commit --author="YOUR_AWESOME_NAME <YOUR_AWESOME_EMAIL>"
```

#### amend author of last commit
```shell
git commit --amend --author="YOUR_AWESOME_NAME <YOUR_AWESOME_EMAIL>"
```

#### amend author from root

1. rebase from root: `git rebase --interactive --root`

2. pick the commit(s) to edit

3. edit author of that specific commit: `git commit --amend --author="ShivakumarSwamy <shivakumarswamy.bg@gmail.com>"` 

4. continue rebase: `git rebase --continue`

5. repeat 3 & 4 n times until all the selected commits are addressed

### sign

#### amend and sign commit with not edit
```shell
git commit --amend -S --no-edit
```

### config

Add `--global` option to set the config globally

#### set locally gpg program
```shell
git config gpg.program gpg
```

#### set locally gpg sign
```shell
git config commit.gpgsign true
```

#### set locally gpg signing key id
```shell
git config user.signingkey <GPG_KEY_ID>
```

#### set locally user name
```shell
git config user.name <YOUR_CHARMING_NAME>
```

#### set locally email
```shell
git config user.email <YOUR_FOO_EMAIL> 
```

## resources
- [how can i change the author name / email of a commit?](https://www.git-tower.com/learn/git/faq/change-author-name-email/)