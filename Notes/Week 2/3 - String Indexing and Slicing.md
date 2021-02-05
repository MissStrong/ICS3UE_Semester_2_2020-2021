## Note – String Indexing and Slicing

### String Indexing

Every character in a string has an **index** (plural: **indices** or **indexes**). The index tells us which position the character is at. The first position is index 0, the second position is index 1, the third position is index 2, and so on.

**In computer science, we often start counting at 0 instead of 1**. Being "off by one" is a common phenomenon when programming.

To extract a specific character in a string, we can use **string indexing**. String indexing involves surrounding the index in square brackets and placing it directly after the string.

```python
s = "abcde"

print(s[0])  # prints a
print(s[1])  # prints b
print(s[4])  # prints e
print(s[5])  # doesn't work since the highest index is 4
```

Suppose we have a long string and we want to extract the last character in it. Instead of manually counting how many characters are in the string, we can use the `len()` function to do that for us.

```python
s = "qwertyuiop[]asdfghjkl;'zxcvbnm,."

print(len(s))  # prints 32
print(s[len(s)-1])  # prints the last character, a period
```

Another option is to use **negative indices**. In Python, we can use negative indices to count backwards from the end of a string.

```python
s = "abcde"

print(s[-1])  # prints the last character, e
print(s[-2])  # prints the second last character, d
print(s[-4])  # prints the fourth last character, b
```

### String Slicing

A **substring** is basically a smaller string inside of a larger string. For example, `"def"` is a substring of `"abcdefgh"`.

We can use **string slicing** to extract a substring. The notation for slicing is similar to indexing, except we specify a **start index** and an **end index** separated by a colon. The character at the end index is *not included* in the substring.

```python
s = "abcdefgh"

print(s[0:5])  # prints abcde
print(s[3:6])  # prints def
print(s[4:len(s)])  # prints efgh
```

If we leave the starting index empty, the default value is `0`. If we leave the ending index empty, the default value is the length of the string.

```python
s = "abcdefgh"

print(s[:5])  # prints abcde, same as s[0:5]
print(s[4:])  # prints efgh, same as s[4:len(s)]
```

We can also use negative indices. Each negative index is treated as their corresponding positive index.

```python
s = "abcdefgh"

print(s[1:-2])  # prints bcdef, same as s[1:6]
print(s[-5:7])  # prints defg, same as s[3:7]
print(s[-6:-3])  # prints cde, same as s[2:5]
```

Whenever the start index is greater or equal to the end index, the resulting substring is an **empty string**. An empty string has a length of zero and is expressed like this: `""`. If we try to print an empty string, it won't print anything.

```python
s = "abcdefgh"

print(s[1:1])  # nothing happens
print(s[6:5])  # nothing happens
print(s[-3:3])  # same as s[5:3], so nothing happens
print(s[7:-3])  # same as s[7:5], so nothing happens
```

