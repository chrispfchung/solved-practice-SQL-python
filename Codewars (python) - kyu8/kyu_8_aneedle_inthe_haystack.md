**Challenge:** <https://www.codewars.com/kata/a-needle-in-the-haystack/train/python>

**Problem:**
Can you find the needle in the haystack?

Write a function findNeedle() that takes an array full of junk but containing one "needle"

After your function finds the needle it should return a message (as a string) that says:

"found the needle at position " plus the index it found the needle, so:

find_needle(['hay', 'junk', 'hay', 'hay', 'moreJunk', 'needle', 'randomJu

**Thought Process:**
I want to use a loop to get through the list. I also want to use an '==' to
match the word to "needle". Since I also need to return the index of the word,
I added a counter that adds one after each time through the loop. Finally,
I added a '.format' to input my count of where the word was. Initially I had
'index_count = 0' but found that my answer would be 1 count off because adding 1
from the start when getting to the first  word would make it 1, not 0.

```python
def find_needle(haystack):
    index_count = -1
    for word in haystack:
        index_count += 1
        if word == 'needle':
            return "found the needle at position {}".format(index_count)

```
