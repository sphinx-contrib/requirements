# sphinxcontrib-requirements
A Sphinx extension allowing declaration if requirement specs wherever in the
documentation (for instance, in docstrings of UnitTest.test_* methods) and
collating them in a single list.

## Installation
Install this package with pip:

```shell script
pip install sphinxcontrib-requirements
```

and enable in project configuration (`conf.py`):

```python
extensions = [
    'sphinxcontrib.requirements',
]
```

## Usage
The requirements extension provides two new directives:

### requirement
Defines an individual requirement to be processed. 

#### Options
The `status` option defines the disposition of the requirement. Values are 
currently fixed to the following values:

* `undecided` (default)
* `todo`
* `done`
* `tested`
* `wontfix`

A future version shall have the ability to control the available options through
the Sphinx `conf.py` file.

The `reference` option allows an external document reference to be specified
such as a formal requirements document or specification.

### reqlist
The `reqlist` directive is replaced by a list of all the requirements that have
been found across the documentation. Much like the built-in `todo` extension,
this directive can only be processed properly if a complete build of the
documentation is run (i.e `make clean` is run first,) otherwise unchanged files 
aren't processed.

## Configuration
No configuration is necessary at this time.


