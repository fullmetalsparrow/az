### Redirect STDERR to STDOUT
---
``` bash
$ find . -name {file} 2>&1
```


### Redirect STDOUT and STDERR to File
---
``` bash
$ find . -name {file} 2>&1 > {log-file}
```