# Python/CouchDB
## Installation

    pip install CouchDB

Prerequisites:
*   simplejson (or Python >= 2.6, which comes with a simplejson-based JSON module in the standard library)
*   Python 2.6 or later
*   CouchDB 0.10.x or later (0.9.x should probably work, as well)

## Usage

```python
import json
import couchdb

couch = couchdb.Server('http://localhost:5984/')
couch.resource.credentials = ("admin", "admin")
db = couch['db_name']
doc = {'foo': 'bar'}
db.save(doc)
db.save(json.loads(json.dumps(my_dict))) # create new document with a dict
```

## References
*   [http://pythonhosted.org/CouchDB](couchdb-python on Python Hosted)
*   [https://github.com/djc/couchdb-python](GitHub)
*   [https://pypi.python.org/pypi/CouchDB](PiPy)
