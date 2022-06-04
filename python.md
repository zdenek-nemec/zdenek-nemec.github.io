# Python

## Usage

### For-Cycle

```python
for item in items:
    if item == 1:
        break
else:
    print("No item is 1")
```

### Exceptions

Sources

* [Python Documentation](https://docs.python.org/3/tutorial/errors.html)

```python
try:
    x = int(input("Please enter a number: "))
    break
except ValueError:
    print("Oops!  That was not a valid number.")
```

### Yield

Code sample:

```python
def generate_number():
    yield 0
    yield 1
    for i in range(2, 5):
        yield i

print(generate_number())
for i in generate_number():
    print(i)
```

Console output:

```text
<generator object generate_number at 0x00D14798>
0
1
2
3
4
```
