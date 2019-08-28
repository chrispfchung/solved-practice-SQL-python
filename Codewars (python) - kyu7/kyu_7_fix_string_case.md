
### Source: <https://www.codewars.com/kata/5b180e9fedaa564a7000009a/train/python>

1. given string with mixed upper and lower (or all of one type)
2.  convert to either lower or upper
3.  if string equal lower & upper, lower it
4.  make as few changes as possible

## Method
1. Create upper and lower count variables
2. Confirm upper or lower in string and add to count
3. If uppercase more than lower, return string as uppercase
4. Otherwise return all lowercase

## My Solution

```python
def solve(s):
    upper_count = 0
    lower_count = 0
    for ele in s:
        if ele == ele.upper():
            upper_count += 1
        else:
            lower_count += 1
    if upper_count > lower_count:
        return s.upper()
    else:
        return s.lower()
```

## My Notes
Initially I did not want to go the route of creating and upper and lower count variable. I wanted to try using a len(s.upper()) which I wanted to give me the number of uppercases that were in the string. However I think that would only give me the length of the string. I went online to see if I could find another way but ultimately resorted back to the lower and upper count.
ele == ele.upper() was a good way to see if it was an uppercase letter.
