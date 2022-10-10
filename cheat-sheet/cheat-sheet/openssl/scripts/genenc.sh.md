``` bash
#!/usr/bin/bash

if [[ -z $@ ]]; then
        OUTFILE="passwd.enc"
else
        while getopts "o:" OPT; do
                OUTFILE=${OPTARG}
        done
fi

echo $RANDOM | md5sum | head -c 20 > $OUTFILE
openssl enc -aes256 -pbkdf2 -salt -in $OUTFILE -out $OUTFILE
```