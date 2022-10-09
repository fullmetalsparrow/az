### Generate New Keys
---
``` bash
$ ssh-keygen -t ed25519 -C "email"
```

> For legacy systems, use:
> `$ ssh-keygen -t rsa -b 4096 -C "email"`


### Add SSH Key to the ssh-agent
---
``` bash
$ eval "$(ssh-agent -s)"
$ ssh-add ~/.ssh/id_ed25519
```


### Add Public SSH Key to GitHub
---
``` bash
$ cat ~/.ssh/id_ed25519.pub
```
Location of GitHub keys: User > Settings > SSH and GPG keys


### Test SSH Connection to GitHub
---
``` bash
$ ssh -T git@github.com
```


### Change Key Passphrases
``` bash
$ ssh-keygen -p -f ~/.ssh/id_ed25519
```
