<code>8""""8                           8""""8                         
    8      eeeee eeeee eeeee eeee    8      eeeee e    e e     eeee 
    8eeeee   8   8   8   8   8       8eeeee   8   8    8 8     8    
        88   8e  8eee8   8e  8eee        88   8e  8eeee8 8e    8eee 
    e   88   88  88  8   88  88      e   88   88    88   88    88   
    8eee88   88  88  8   88  88ee    8eee88   88    88   88eee 88ee </code>

A Python library that standardizes the names of U.S. states

[![](https://travis-ci.org/datadesk/latimes-statestyle.png)](https://travis-ci.org/datadesk/latimes-statestyle)

Features
--------

-   Submit a state’s name, postal abbreviation or [FIPS
    code](https://en.wikipedia.org/wiki/Federal_Information_Processing_Standards)
    and receive a clean object with all other formats as attributes.
-   State objects also provide the “stateface” code for [ProPublica’s
    web font of state shapes](http://propublica.github.com/stateface/)

Getting started
---------------

Getting started is as easy as…

```bash
$ pip install latimes-statestyle
```

Then start feeding it your data:

```python
>>> import statestyle
>>> obj = statestyle.get('CA')
>>> print obj.name
California
>>> print obj.postal
CA
>>> print obj.ap
Calif.
>>> obj = statestyle.get(6)
>>> print obj.name
California
>>> obj.stateface
"E"
>>> statestyle.get("foo")
Traceback (most recent call last):
    File "<stdin>", line 1, in <module>
    File "statestyle/__init__.py", line 27, in get
    raise ValueError("The state you requested does not exist")
ValueError: The state you requested does not exist</code>

Contributing
------------

If you would like to add another feature or change existing data, edit
`statestyle/data.csv` and then run `python build.py`, which will remake
the data file imported by the library.
