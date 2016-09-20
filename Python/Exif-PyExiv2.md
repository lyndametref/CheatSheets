 # PyExiv2 for Exif image tags management
 ## Installation



```python
import pyexiv2
tags = pyexiv2.ImageMetadata(full_path)  #full_path: path of image
tags.read() # reads the tags from the image and build the dictionary
tags[1].raw_value # return string with value
```

 ## References
*   [http://python3-exiv2.readthedocs.io/en/latest/index.html](Read the docs)
*   [https://pypi.python.org/pypi/py3exiv2/0.2.1](Pypi.Python.org)
