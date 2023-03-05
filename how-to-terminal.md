# How to do stuff in terminal

### List, select, and copy

```bash
#!/bin/bash
for slurmOutFileName in $(ls ./*.out)
do
	# if the file has one or more lines
    if [ $(wc -l < $slurmOutFileName) != 0 ]
    then
      echo $slurmOutFileName
      echo $(wc -l < $slurmOutFileName)  
      rsync -av $slurmOutFileName outFiles/
    fi
done
```

