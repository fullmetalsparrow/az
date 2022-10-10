### Concatenate Multiple Lines in STDIN to File
---
``` bash
$ cat << EOF > {file-path}
some text
EOF
```
*This allows for using expansion operations and variables in between EOF*

``` bash
$ cat << "EOF" > {file-path}
some more text
EOF
```
*Everything is taken to be a string literal (no bash operations will run in between EOF)*