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
tree -L 2
```

### find and replace
```
#!/bin/bash

for fileName in $(ls */*/*/*deg/*/SIM*.sh)
do
  reasFileName=( ${fileName//.sh/.reas} )
  inpFileNameDummy=( ${fileName//.sh/.inp} )
  inpFileName=( ${inpFileNameDummy//SIM/RUN} )

  # change from epos-urqmd to sibyll-urqmd in .sh file
  sed -i 's;EPOS_urqmd;SIBYLL_urqmd;'g $fileName
  sed -i 's;epos-urqmd;sibyll-urqmd;'g $fileName

  # change from epos-urqmd to sibyll-urqmd in .reas file
  sed -i 's;epos-urqmd;sibyll-urqmd;'g $reasFileName

  # change from epos-urqmd to sibyll-urqmd in .inp file
  sed -i 's;epos-urqmd;sibyll-urqmd;'g $inpFileName

  # change from EPOS to SIBYLL and EPOSIG to SIBSIG in .inp file
  sed -i 's;EPOS T 0;SIBYLL T 0;'g $inpFileName
  sed -i 's;EPOSIG T;SIBSIG T;'g $inpFileName

  # delete the line containing the strind EPOPAR
  sed -i '/EPOPAR/d' $inpFileName

done
```
### Disk usage
check out: https://opensource.com/article/18/7/how-check-free-disk-space-linux
```
# Nice interface and shows the space occupied by the contents individually. 
fcdu . 

# show the total space used by the directory
du -sh .

# occupied and available space in a disk
df -h
```
