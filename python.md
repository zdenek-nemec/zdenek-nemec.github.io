# Python

## Yield

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
