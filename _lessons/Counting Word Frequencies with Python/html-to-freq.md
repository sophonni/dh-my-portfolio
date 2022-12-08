---
layout: page
title: Counting Word Frequencies with Python
description: By having a clean list, it's enchance our ability to its content in a meaningful way. Counting the frequency of specific words in the list can provide illustrative data. Python has an easy way to count frequencies, but it requires the use of a new type of variable: the dictionary. Before you begin working with a dictionary, consider the processes used to calculate frequencies in a list.
---

## Source
[William J. Turkel and Adam Crymble, "Counting Word Frequencies with Python" Programming Historian, https://doi.org/10.46430/phen0078.](https://programminghistorian.org/en/lessons/counting-frequencies)


## A program which takes a URL and returns word-frequency pairs for the web page, sorted in order of descending frequency

```python
# html-to-freq-2.py

import urllib.request, urllib.error, urllib.parse
import obo

url = 'http://www.oldbaileyonline.org/browse.jsp?id=t17800628-33&div=t17800628-33'

response = urllib.request.urlopen(url)
html = response.read().decode('UTF-8')
text = obo.stripTags(html).lower()
fullwordlist = obo.stripNonAlphaNum(text)
wordlist = obo.removeStopwords(fullwordlist, obo.stopwords)
dictionary = obo.wordListToFreqDict(wordlist)
sorteddict = obo.sortFreqDict(dictionary)

for s in sorteddict: print(str(s))
```
