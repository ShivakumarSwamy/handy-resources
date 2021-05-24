
### list public and private gpg keys

```shell
gpg --list-secret-keys --keyid-format LONG
```

### generate gpg key

```shell
gpg --full-generate-key
```

### output gpg public key

```shell
gpg --armor --export <GPG_KEY_ID>

# mac: copy to clipboard
gpg --armor --export <GPG_KEY_ID> | pbcopy
```

### troubleshooting mac gpg for below error

```text
error: gpg failed to sign the data
fatal: failed to write commit object
```

Solution: [Source](https://stackoverflow.com/questions/39494631/gpg-failed-to-sign-the-data-fatal-failed-to-write-commit-object-git-2-10-0)
```shell
brew upgrade gnupg
brew install pinentry-mac
echo "pinentry-program /usr/local/bin/pinentry-mac" >> ~/.gnupg/gpg-agent.conf
killall gpg-agent
```


### resource
- [managing commit signature verification](https://docs.github.com/en/github/authenticating-to-github/managing-commit-signature-verification)