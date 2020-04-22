## question
快速幂和快速幂取模, 复杂度O(logN)
递归快速幂，二分思想
## code
递归快速幂
```python
def fastPow(base, exp):
	if exp == 0:
		return 1
	else exp % 2 == 1:
		return fastPow(base, exp-1)*base
	else:
		tmp = fastPow(base, exp / 2)
		return tmp*tmp
```
```python
def fastPow(base, exp):
	res = 1
	while exp:
		b = exp & 1
		if  b !=0:
			res *=base
		base *=base
		exp = exp >> 1
	return res
```

```python
def fastPow(base, exp, c):
	res = 1
	while exp:
		b = exp & 1
		if  b !=0:
			res =  (res*base) % c
		base = (base*base) % c
		exp = exp >> 1
	return res
```