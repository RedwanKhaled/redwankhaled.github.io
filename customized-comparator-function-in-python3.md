##### In python2, we used to have `cmp` keyword in sort function to add a customized comparator. However, this `cmp` is not anymore in python3. Instead of this a `cmp_to_key` is added in `functools` library.
#### 
```python
from functools import cmp_to_key
def my_cmp(a, b):
	# If the numeric values are same
	# then do the string comparison
	if a[1] == b[1]:
		if a[0] < b[0]:
			return -1
		elif a[0] == b[0]:
			return 0
		else:
			return 1
	# Otherwise, do number comparison
	# negative means a < b
	# 0 means a == b
	# positive means a > b
	return a[1] - b[1]

x = {'a': 1, 'b': 10, 'c': 5, 'd': 0, 'e': 1}
sorted(x.items(), key=cmp_to_key(my_cmp))
```
