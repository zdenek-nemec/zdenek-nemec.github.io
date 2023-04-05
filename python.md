# Python

## Command Line Interface

| Command                       | Description    |
| ----------------------------- | -------------- |
| `python -m unittest discover` | Run unit tests |

## Code

### For-Cycle

```python
for i in range(10):
    if i == 3:
        break
else:
    print("Not found")
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

```python
def generate_number():
    yield 0
    yield 1
    for i in range(2, 5):
        yield i

print(generate_number())
for i in generate_number():
    print(i)

# Output:
# <generator object generate_number at 0x00D14798>
# 0
# 1
# 2
# 3
# 4
```

### Match

Python 3.10+

```python
command = "delete"
match command:
     case "show":
         print("Show")
     case "remove" | "delete":
         print("Remove")
     case _:
         print("Unknown")
```

### F-String

Expansion via `=` is available in Python 3.8+

```python
number = 3.14159
print(f"F-string print: {number} {number=} {number=:,.2f}")

# Output:
# F-string print: 3.14159 number=3.14159 number=3.14
```

### Walrus Operator

Python 3.8+

```python
phone_number = "420731234567"
for length in range(len(phone_number), 2, -1):
    if (prefix := phone_number[0:length]) in ["420731", "421"]:
        print(prefix)
        break
else:
    print("Not found")
```
