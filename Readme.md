# A thresholding algorithm for clustering

This is a (naive) Python implementation of a simple thresholding algorithm for clustering under a pairwise
 similarity measure. The algorithm was designed and analyzed by Aurko Roy, Sadra Yazdanbod and Daniel Zink
 and shown to recover the * target * clustering if the similarity function satisfies the following stability
property

```
k(A, X) > k(A, Y) 
```

for every triple of sets A, X and Y such that A and X belong to the same cluster in the * target * cluster
while the set Y is a subset of points in some other cluster. The algorithm is noise stable in the sense that
it only requires sets A, X and Y above a certain size limit to satisfy this property. The algorithm can be 
optimized to run in time O(n^4), but the present implementation is a pretty naive one. I will put up a link to
the manuscript soon.

## Dependencies
 - [numpy](http://www.numpy.org/)
 - [scipy](http://www.scipy.org/)
 - [munkres](https://pypi.python.org/pypi/munkres/)

## Installation
The following will install the algorithm

```shell
sudo setup.py install
```

## Usage
To run the actual algorithm type the following in a python interpreter

```python
from ryzcluster import cluster
cluster.test(data, k, e)
```
where data is path to the data file, k denotes the number of clusters in your target and e is a number
between 0 and 1 which denotes the minimum fraction of points contained in a single cluster in your target.