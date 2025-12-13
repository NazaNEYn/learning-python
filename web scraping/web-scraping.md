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


## How to get all tags (`find_all()`)
`find_all()` returns a `list`.

```python
print(soup.find_all(name="li"))
print(soup.find_all(name="a"))
print(soup.find_all(name="p"))
```


## How to get the texts from an anchor tag

```html
  <a href="https://x.com/nazanin_ashrafi">My Hobbies</a>
  <a href="https://x.com/nazanin_ashrafi">Contact Me</a>
```

```python
all_anchors = soup.find_all(name="a")

for tag in all_anchors:
    print(tag.get_text())
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

## How to find first matching child tag

**By an`id`:**

```html
  <h1>Hellooooo</h1>
  <h1 id="name">Naz Ashrafi</h1>
```

```python
heading = soup.find(name="h1", id="name")
print(heading)
# <h1 id="name">Naz Ashrafi</h1>
```

**By a`class`:**

*Note:* <br>
Make sure you use `class_`

```html
  <h3 class="book">Books</h3>
  <h3 class="heading">Books and Teaching</h3>
```

```python
heading = soup.find(name="h3", class_="heading")
print(heading)
# <h3 class="heading">Books and Teaching</h3>
```

## CSS selector

* `select_one()` gives you the **first** matching item in a list.
* `select()` gives you **all** of the matching items in a list.

```html
  <p>
    <em>Founder of 
      <strong>
        <a href="https://x.com/nazanin_ashrafi">Hello world</a>
      </strong>.
    </em>
  </p>
```

```python
url = soup.select_one(selector="p a")
print(url)

# <a href="https://x.com/nazanin_ashrafi">Hello world</a>
```

## CSS selector by `id`

```html
  <h1 id="name">Naz Ashrafi</h1>
```

```python
heading = soup.select_one(selector="#name")
print(heading)

# <h1 id="name">Naz Ashrafi</h1>
```

## CSS selector by `classes`

```html
  <h3 class="heading">Books and Teaching</h3>
```

```python
heading = soup.select_one(selector=".heading")
print(heading)

# <h3 class="heading">Books and Teaching</h3>
```


----------------------------------


# Web scraping a live website:

### What does “A Live Website” Mean for Web Scraping?

In the context of web scraping, the term "live website" generally refers to a site that presents challenges beyond simple static HTML retrieval. It usually implies one or more of the following characteristics:

* **Dynamic Content Changes:** A website that is constantly updated with new content, requiring your scraper to check frequently for fresh data (e.g., a news feed or stock ticker).
* **Dynamic Data Loading (JavaScript):** A website that loads its main content *after* the initial HTML document has loaded, relying on client-side JavaScript to fetch data asynchronously (e.g., using AJAX or API calls). If you use a standard library like **Requests**, you will only get the initial, empty HTML shell.
* **Bot Protection:** A website that actively employs technologies to detect and block automated access, such as:
    * Checking for expected browser **headers** (like `User-Agent`).
    * Verifying and setting **cookies**.
    * Implementing advanced challenge/response systems like **Cloudflare** or **reCAPTCHA**.

Web scraping a "live website" requires choosing the right tools based on how the site loads its data. For example, sites heavily reliant on JavaScript often require a tool like **Selenium** to run the JavaScript and render the full page before scraping.

## Web Scraping Strategy: Static vs. Dynamic Sites

The strategy and tools you choose for web scraping depend entirely on the nature of the target website's content rendering.

| Feature | Static Website | Dynamic Website (JavaScript) |
| :--- | :--- | :--- |
| **Data Source** | Data is present directly in the **initial HTML source code**. | Data is fetched via **JavaScript** (AJAX/API calls) *after* the initial page load. |
| **Tool Used** | **Requests** + **BeautifulSoup** (or `lxml`). | **Selenium** or **Playwright** (Headless browser) + **BeautifulSoup**. |
| **Complexity** | Low to Moderate. | Moderate to High. |
| **Speed/Resources** | Very fast and low resource usage. | Slower and higher resource usage (must load a full browser instance). |
| **How to Check** | View page source (Ctrl+U or Cmd+Option+U). If the content is there, it's static. | View page source. If the content is missing, check the Network tab in Dev Tools for API calls. |

<br> <br>

* **1: Live site with static HTML**

```python
import requests
from bs4 import BeautifulSoup

url = "https://example.com"

response = requests.get(url, headers=headers)
web_page = response.text
soup = BeautifulSoup(web_page, "html.parser")
```

* **2: Live site that blocks bots (403 errors)**

```python
import requests
from bs4 import BeautifulSoup

url = "https://www.imdb.com/chart/top"

headers = {"User-Agent": "Mozilla/5.0", "Accept-Language": "en-US,en;q=0.9"}

response = requests.get(url, headers=headers)
soup = BeautifulSoup(response.text, "html.parser")
```

* **3: JavaScript-rendered live websites**
