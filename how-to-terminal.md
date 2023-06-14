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

### select files based on length and delete if shorter than a chosen length
```
#!/bin/bash

for fileName in $(ls ./75deg/*/SIM*.list)
do
  echo $fileName
  if [ $(wc -l < $fileName) < 3 ]
  then
    echo $fileName
    echo $(wc -l < $fileName)
    $fileName >> deleteThese.txt
  fi
done
```

### Output directory tree
```
tree
```
