# How to do stuff in Python

## Fundamentals
### Data Structures
**Dictionaries**: 

```python3
mydict = {'fit_poly' : [1,2,3], 'fit_sin' : [1,2.5,6]}
other_dict['new_poly'] =  [2,4,5]
other_dict['diff_sin'] = [5,1,1]
```

Write the dictionary to a file: I haven't figured it out yet.

## I/O

Read a file line by line and split the string
```
inFile = open(inFileName1, 'r')
lines = inFile.readlines()
for line in lines:
    if('PARAMETERS' in line):
        header, values = line.split('=')
        par1, par2, par3, par4, par5, par6 = values.split()
```
`split()` without argument splits the string around spaces by default.

Find files using a wildcard
```
import glob
for name in glob.glob('dir/*'):
    print(name)
```
## Libraries

### Numpy

### Scipy
-   [Robust linear model estimation using RANSAC](https://scikit-learn.org/stable/auto_examples/linear_model/plot_ransac.html)


### Matplotlib
Make better figures: 
-   [Making publication-quality figures in Python](https://towardsdatascience.com/making-publication-quality-figures-in-python-part-i-fig-and-axes-d86c3903ad9b)
-   [Publication-quality plots](https://python4astronomers.github.io/plotting/publication.html)
-   [Preparing figures for publications and presentations](https://www.mrl.ucsb.edu/~seshadri/PreparingFigures-June2019.pdf)

Custom legend markers
```
import matplotlib.lines as mlines
rdMarker = mlines.Line2D([], [], color='orange', marker='o', alpha = 0.7, linestyle='None',
                      markersize=4, label='RD Th {}'.format(T1Threshold))
rdSdMarker = mlines.Line2D([], [], color='black', marker='.', alpha = 0.7, linestyle='None',
                      markersize=4, label='WCDT3')

plt.legend(handles=[rdMarker, rdSdMarker])
```

### Pandas

```py
df = pd.read_csv("raw_4167.dat", header=None, delimiter=r"\s+")

df.columns = ['col0', 'col1', 'col2', 'col3']


```

### Jupyter

convert `.ipynb` to python script

```
jupyter nbconvert --to script name.ipynb
```
Show inline figures in better resolution
```
%config InlineBackend.figure_format = 'retina'
```
