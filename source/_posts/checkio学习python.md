---
title:  checkio 通过练习学习python- Home篇
date: 2017-08-20 10:05:36
tags:
- python
- checkio
categories:
- python
- checkio
---
# The Most Wanted Letter
{% note info %} 
    问题：已知一个字符串，求出现次数最多的字母。次数相同时取latin alphabet靠前的字母。
    
{% endnote %}

{% note success %} 
方案：巧妙利用内置函数max，并将函数当作参数(text.count是一个函数)统计数量，简直perfect。
{% endnote %} 
{% codeblock lang:python %}
    import string
    ​
    def checkio(text):
        """
        We iterate through latyn alphabet and count each letter in the text.
        Then 'max' selects the most frequent letter.
        For the case when we have several equal letter,
        'max' selects the first from they.
        """
        text = text.lower()
        return max(string.ascii_lowercase, key=text.count)
{% endcodeblock %}

# Non unique elements
{% note info %} 
    问题：已知一个数组，求其移除不重复元素的结果。即数组中只保留重复元素，并保持其原来顺序。
{% endnote %}
{% note success %} 
    方案1：遍历数组，计算其数量是否大于1
{% endnote %}
{% codeblock lang:python %}
    ​
    def checkio(data):
        # 列表生成式 + if
        return [x for x in data if data.count(x) > 1]
    
    def checkio(data):
        # 当然还可以换种写法
        return list(filter(lambda i: data.count(i) - 1,data))
{% endcodeblock %}
{% note success %} 
    方案2：利用Counter类进行统计数量，然后遍历判断数量是否大于1。| 也可以构造一个一元素数量全为1的Counter类，然后进行相减
{% endnote %}
{% codeblock lang:python %}
    def checkio(data):
        from collections import Counter
        count = Counter(data)
        return [x for x in data if x in count[x] > 1]

    def checkio(data):
        from collections import Counter
        nonunique = Counter(data) - Counter(set(data))
        return [x for x in data if x in nonunique]
    
{% endcodeblock %}
{% note success %} 
    方案3：双桶思想，一个桶放唯一的元素，一个桶放重复的元素。最后遍历选择重复的元素。
{% endnote %}
{% codeblock lang:python %}
    def checkio(sequence):
        bins = seen, nonunique = set(), set()
        for number in sequence: bins[number in seen].add(number)
        return [number for number in sequence if number in nonunique]
{% endcodeblock %}
# House Password
{% note info %} 
    问题：判断密码是否符合规定，要求大于等于10个字符，至少包含一个大写字母、小写字母、数字。
{% endnote %}