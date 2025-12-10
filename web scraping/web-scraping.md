# What is web scraping?
We can use a websire's API to access their data or to interact with website using code. But some websites don't have an API or their API doesn't let us do all thethings that we want to do.<br>
This is where `web scraping` comes in.<br>
By web scraping we look through the unerlying `HTML` code of a website to get hold of the information that we want. 

# BeautifulSoup
`BeautifulSoup` is a module that helps developers to make sense of websites. It helps you read, search, and extract information from HTML or XML webpages.


## Create a soup 
Install `BeautifulSoup` first and then import it.

```python
from bs4 import BeautifulSoup

soup = BeautifulSoup(html_content, "html.parser")
```


```html
<!DOCTYPE html>
<html>

<head>
  <meta charset="utf-8">
  <title class="title-class">My Personal Site</title>
</head>

<body>
  <h1 id="name">Naz Ashrafi</h1>
  <p>
    <em>Founder of 
      <strong>
        <a href="https://x.com/nazanin_ashrafi">Hello world</a>
      </strong>.
    </em>
  </p>
  <p>I am an iOS and Web Developer. I love coffee and code.</p>
  <hr>
  <h3 class="heading">Books and Teaching</h3>
  <ul>
    <li>The Complete iOS App Development Bootcamp</li>
    <li>The Complete Web Development Bootcamp</li>
    <li>100 Days of Code - The Complete Python Bootcamp</li>
  </ul>
  <hr>
  <h3 class="heading">Other Pages</h3>
  <a href="https://x.com/nazanin_ashrafi">My Hobbies</a>
  <a href="https://x.com/nazanin_ashrafi">Contact Me</a>
</body>

</html>
```


## How to get any elements/tags

```python
with open("website.html") as file:
    data = file.read()
    
soup = BeautifulSoup(data, "html.parser")

head = soup.head
title = soup.title
paragraph = soup.p 
```

*Note:* This is only get to get the **first** element.


## How to get the name of the tags

```python
head = soup.head.name
title = soup.title.name
paragraph = soup.p.name

print(head,title,paragraph)
# head title p
```

## How to get the texts from tags
If the tag contains only text (no other nested tags), returns that text string. Otherwise, returns `None`.

```python
head = soup.head.string
title = soup.title.string
paragraph = soup.p.string

print(head,title,paragraph)
# None My Personal Site None
```


## How to get the texts from a anchor tag

```html
  <a href="https://x.com/nazanin_ashrafi">My Hobbies</a>
  <a href="https://x.com/nazanin_ashrafi">Contact Me</a>
```

```python
all_anchors = soup.find_all(name="a")

for tag in all_anchors:
    print(tag.getText())
```

## How to get the links from a anchor tag

```html
  <a href="https://x.com/nazanin_ashrafi">My Hobbies</a>
  <a href="https://x.com/nazanin_ashrafi">Contact Me</a>
```

```python
all_anchors = soup.find_all(name="a")

for tag in all_anchors:
    print(tag.get("href"))
```

