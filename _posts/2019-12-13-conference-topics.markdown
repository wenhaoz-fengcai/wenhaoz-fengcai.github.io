---
layout: single
title:  "WordCloud visualization of conference topics"
date:   2019-12-13 11:30:00 -0700
categories: Academic Conference
tags: [academic]
toc: true
publish: true
---
IEEE BigData conference was just over this past Thursday. Do you wanna know what is going on currently in big data mining research area? the hot research topics/keywords that were discussed in the conference proceedings? Man, wouldn't it be better if I can **see** the hot research topics and keywords. Worry no more, this is where wordcloud can help you capture the info within seconds.

![](https://blogassetswenhao.s3-us-west-1.amazonaws.com/wordclod/wordcloud.png)

Here is the code snippet that I used to generate this wordCloud.


```python
from wordcloud import WordCloud

# read source text and do a bit preprocessing
with open("bigdata.txt") as file:
    inputf = file.readlines()
    res = []
    for line in inputf:
        sp = line.split(",")
        res.append(sp[-1])
	res_str = " ".join(res)

	# remove some words that are not interesting
	stopwords = ['based','using','high','learning', "via", "network"]
	querywords = res_str.split()

	resultwords  = [word for word in querywords if word.lower() not in stopwords]
	result = ' '.join(resultwords)
	
	# create wordcloud with max font size = 40
	wordcloud = WordCloud(max_font_size).generate(result)
	
	# show the wordcloud
	import matplotlib.pyplot as plt
	plt.imshow(wordcloud, interpolation='bilinear')
	plt.axis("off")
	plt.show()
```

The sample input file can be seen [here](https://blogassetswenhao.s3-us-west-1.amazonaws.com/wordclod/bigdata.txt). These are the accepted regular paper and short papers in IEEE BigData 2019 conference. Each line is a individual paper work. Author names and titles are separated by ``,".
