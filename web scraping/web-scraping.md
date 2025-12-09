# What is web scraping?
We can use a websire's API to access their data or to interact with website using code. But some websites don't have an API or their API doesn't let us do all thethings that we want to do.<br>
This is where `web scraping` comes in.<br>
By web scraping we look through the unerlying `HTML` code of a website to get hold of the information that we want. 

# BeautifulSoup
`BeautifulSoup` is a module that helps developers to make sense of websites. It helps you read, search, and extract information from HTML or XML webpages.

## Examples:

### How to get the texts from a anchor tag

```html
  <a href="https://x.com/nazanin_ashrafi">My Hobbies</a>
  <a href="https://x.com/nazanin_ashrafi">Contact Me</a>
```

```python
all_anchors = soup.find_all(name="a")

for tag in all_anchors:
    print(tag.getText())
```

### How to get the links from a anchor tag

```html
  <a href="https://x.com/nazanin_ashrafi">My Hobbies</a>
  <a href="https://x.com/nazanin_ashrafi">Contact Me</a>
```

```python
all_anchors = soup.find_all(name="a")

for tag in all_anchors:
    print(tag.get("href"))
```

