# A nuance about importing stuff in Python.

---

A folder called `a` contains a file called `foo.py`:

---?code=a/foo.py&title=a/foo.py

---

```
>>> from a import foo
>>> foo
<module 'a.foo' from 'a/foo.py'>
>>> foo.MY_THING
'THIS IS A STRING DEFINED IN THE MODULE'

```

---

Folder `b` defines `foo` in the init file:

---?code=b/__init__.py&title=b/\_\_init\_\_.py

---

```
>>> from b import foo
>>> foo
'THIS IS A STRING DEFINIED IN __init__.py'

```

---

Folder `c` has a file named `foo.py` AND a symbol `foo` in the init:

---?code=c/__init__.py&title=c/\_\_init\_\_.py
---?code=c/foo.py&title=c/foo.py

---

```
>>> from c import foo
>>> foo
'THIS IS A STRING DEFINIED IN __init__.py'
>>> import c
>>> c.foo
'THIS IS A STRING DEFINIED IN __init__.py'

```

---

```
>>> from c.foo import MY_THING
>>> MY_THING
'THIS IS A STRING DEFINED IN THE MODULE'
>>> import c.foo
>>> c.foo
<module 'c.foo' from 'c/foo.py'>
>>> c.foo.MY_THING
'THIS IS A STRING DEFINED IN THE MODULE'

```
