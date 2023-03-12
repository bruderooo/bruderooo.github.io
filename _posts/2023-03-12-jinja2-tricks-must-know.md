---
layout: post
title: "Jinja 2 tricks you must know"
date: 2023-03-12
---
Hello there, I am {{ author }}. This is my first post, and I hope you like it. Okay, so lets start!
{% raw %}
# Introduction
Jinja is a template engine for Python. It is used to generate text files. In this post, I will be 
showing you some features of Jinja. It is very easy to use, and you will love it. The main syntax 
of Jinja is `{{ }}`. It is used to print variables. For example, if you have a variable `name`, 
you can print it using `{{ name }}`. 

Lets see some examples.
```txt
{{ 1 + 1 }}             # Gives 2
{{ print("Hello") }}    # Gives Hello
{{ name.upper() }}      # Gives NAME
{{ [1, 2, 3] }}         # Gives [1, 2, 3]
{{ {"name": "John"} }}  # Gives {"name": "John"}
{{ (1, 2, 3) }}         # Gives (1, 2, 3)
```

To render file from a template string, you can use Python code like bellow:
```python
from jinja2 import Template

template = Template("Hello {{ name }}")
rendered = template.render(name="John")
```
and in this code variable `rendered` have value `Hello John`.

You can also use code bellow to render a file:
```python
from jinja2 import Environment, FileSystemLoader

env = Environment(loader=FileSystemLoader("templates"))
template = env.get_template("index.html")
rendered = template.render(name="John")
```
and in this code, variable `rendered` have content of file `index.html` with swapped tag `{{ name }}` to value `John`.

# Jinja Features
Jinja is very powerful. It has loops, functions and conditions. Lets see some examples.

### Loops
To loop over a list, you can use `for` loop. For example, if you have a list `names`, you can loop over it like this:
```txt
{% for name in names %}
    {{ name }}
{% endfor %}
```
and this will print all names in the list.

You can also loop over a dictionary (like in Python). For example, if you have a dictionary `names`, you can loop over it like this:
```txt
{% for key, value in names.items() %}
    {{ key }}: {{ value }}
{% endfor %}
```

### Functions
You can also use functions in Jinja. For example, if you have a function `add`, you can use it like this:
```txt
{{ add(1, 2) }}
```

### Conditions
And obliviously in Jinja you can use conditions. For example, if you have a variable `name`, you can use it like this:
```txt
{% if name == "John" %}
    Hello John
{% else %}
    Hello Stranger
{% endif %}
```

### Filters
Jinja has some built-in filters. You can use them to modify variables. For example, if you have a variable `name`, you can use it like this:
```txt
{{ name | upper }}
```
and this will print `NAME`.


# Conclusion
In this post, I showed you some features of Jinja. I hope you liked it. In next post I will show how to use Jinja to master writing SQL queries. If you have any questions, you can write to me on LinkedIn or send me a email. Thank you for reading!
{% endraw %}
