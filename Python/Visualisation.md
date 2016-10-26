# Python Data Visualisation with matplotlib

## Histogram
```
num_bins = 10
plt.hist(my_df.FocalLength, num_bins, normed=0, facecolor='green', alpha=0.5)
```

## Installation and use

    sudo apt install python3-tk
    sudo apt install python-matplotlib


```python
import pandas
import matplotlib
import pylab
import matplotlib.pyplot as plt

matplotlib.style.use('ggplot')

pylab.ion() # activate interactive use
```


## References
*   [http://matplotlib.org/gallery.html]()
*   [http://pandas.pydata.org/pandas-docs/stable/visualization.html]()
