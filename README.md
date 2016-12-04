# iStrings

Simple module to work with interface texts outside of the main code

Normally I use it like
```
from istrings import get_strings as _o, print_into as _
```

So it's very useful to do

```
>>> _('test', my_print_func)
```

or even `print(_o('test'))`

By default all strings are stored in `strings.conf` file divided by sections and reload automatically.

```conf
[test]
This is test section.
You can use multiple lines because I don't care.

[another test]
So be it
```

after that you can use it like this

```python
>>> from istrings import get_strings as _o, print_into as _
>>> _o('test')
['This is test section', 'You can use multiple lines because I don't care']
>>> _o('test2', [])
[]
>>> _('another test', lambda x: print('I said "' + x + '"'))
I said "So be it"
```

To simplify the access there's a kind of sintax sugar object, istr.
```python
>>> from istrings import istr
>>> istr.test
"This is test section.\nYou can use multiple lines because I don't care."
>>> istr.another_test
'So be it'
```

