# python_import_weirdness

```
>>> from a import foo
>>> foo
<module 'a.foo' from 'a/foo.py'>
>>> foo.MY_THING
'THIS IS A STRING DEFINED IN THE MODULE'

```

```
>>> from b import foo
>>> foo
'THIS IS A STRING DEFINIED IN __init__.py'

```

```
>>> from c import foo
>>> foo
'THIS IS A STRING DEFINIED IN __init__.py'
>>> c.foo
Traceback (most recent call last):
  ...
NameError: name 'c' is not defined
>>> import c
>>> c.foo
'THIS IS A STRING DEFINIED IN __init__.py'
>>> from c.foo import MY_THING
>>> MY_THING
'THIS IS A STRING DEFINED IN THE MODULE'
>>> import c.foo
>>> c.foo
<module 'c.foo' from 'c/foo.py'>
>>> c.foo.MY_THING
'THIS IS A STRING DEFINED IN THE MODULE'

```
