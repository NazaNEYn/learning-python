# 1. Introduction
BeautifulSoup works by turning raw HTML/XML into a structured tree.
You typically create a soup like this:

```python
from bs4 import BeautifulSoup

soup = BeautifulSoup(html_content, "html.parser")
```

------

# 2. BeautifulSoup Object (Root Document)

## Common Attributes

| Attribute / Method | Description |
| :--- | :--- |
| **`soup.name`** | Always `"document"` for the root element of the parsed tree. |
| **`soup.contents`** | A **list** of the direct children of the document (tags, strings, etc.). |
| **`soup.children`** | An **iterator** over the direct children of the document. |
| **`soup.text` / `soup.get_text()`** | Extracts all **visible text** content from the document and its descendants, concatenated together. |
| **`soup.prettify()`** | Returns the entire parsed document as a string with **nicely formatted, indented HTML**. |


## Common Methods

| Method | Description |
| :--- | :--- |
| **`find()`** | Finds and returns the **first** matching tag that satisfies the given criteria (name, attributes, text, etc.). |
| **`find_all()`** | Finds and returns a **list of all** matching tags that satisfy the given criteria. |
| **`select()`** | Finds and returns a list of elements using standard **CSS selectors** (e.g., `'#id'`, `'.class'`, `'tag > child'`). |
| **`select_one()`** | Finds and returns the **first** element that matches the given CSS selector. |
| **`get_text(strip=False)`** | Retrieves all text within the tag or document. If `strip=True`, it removes leading/trailing whitespace. |
| **`decompose()`** | Completely **removes a tag** (and all its children) from the parsed tree. |
| **`new_tag(name, attrs={})`** | Creates a **new tag object** with the specified name and optional attributes (the tag is **not yet inserted** into the document). |
| **`new_string(text)`** | Creates a **new `NavigableString`** object from the given text (the string is **not yet inserted** into the document). |


# 3. Tag Object

## Attributes

| Attribute | Description |
| :--- | :--- |
| **`tag.name`** | The **name** of the tag (e.g., `"div"`, `"a"`, `"p"`). |
| **`tag.attrs`** | A **dictionary** containing the tag's HTML attributes and their values. |
| **`tag['attr']`** | A shorthand way to **access the value of a specific attribute** (e.g., `tag['href']`). |
| **`tag.string`** | If the tag contains **only text** (no other nested tags), returns that text string. Otherwise, returns `None`. |
| **`tag.text`** | Returns the **inner text** of the tag, concatenating text from all descendants. Equivalent to `tag.get_text()`. |
| --- | --- |
| **`tag.contents`** | A **list** of the tag's direct children (which can be other tags or strings). |
| **`tag.children`** | An **iterator** over the tag's direct children. |
| **`tag.parent`** | The **parent** element (the tag immediately enclosing it). |
| **`tag.parents`** | A **generator** that yields all ancestor elements (the tag's parent, its parent, and so on). |
| --- | --- |
| **`tag.next_sibling`** | The **next sibling** tag or string *at the same level* in the document tree. |
| **`tag.previous_sibling`** | The **previous sibling** tag or string *at the same level* in the document tree. |
| **`tag.next_element`** | The **next element** in the parse tree, including all descendants, siblings, and ancestors. |
| **`tag.previous_element`** | The **previous element** in the parse tree, including all descendants, siblings, and ancestors. |

## Methods

| Method | Description |
| :--- | :--- |
| **`find(name, attrs)`** | Finds and returns the **first matching child tag** within the current tag, based on tag `name` and optional `attrs` (attributes). |
| **`find_all(name, attrs)`** | Finds and returns a **list of all matching child tags** within the current tag, based on tag `name` and optional `attrs`. |
| **`select(selector)`** | Finds and returns a list of elements using standard **CSS selectors** (e.g., `'.class'`, `'tag > child'`). |
| **`select_one(selector)`** | Finds and returns the **first element** that matches the given CSS selector. |
| **`get(attr, default=None)`** | **Safe attribute lookup**. Returns the value of the attribute `attr`. If the attribute is not found, it returns `None` or the specified `default` value. |
| **`get_text(strip=False)`** | Extracts and concatenates **all text** inside the tag and its descendants. If `strip=True`, it removes leading/trailing whitespace. |
| --- | --- |
| **`clear()`** | Removes **all contents and children** from the tag, leaving the tag itself empty (`<tag></tag>`). |
| **`decompose()`** | Completely **removes the tag and all its contents** from the parse tree and destroys the object. |
| **`extract()`** | **Removes the tag** and its contents from the parse tree, but **returns the tag object**, allowing you to reuse it. |
| **`replace_with(new_tag)`** | Replaces the current tag with a `new_tag` or string, and returns the old tag. |
| **`wrap(wrapper_tag)`** | Wraps the current tag with a new enclosing tag object (`wrapper_tag`). |
| **`unwrap()`** | Removes the tag itself, but keeps its contents in place. The **contents replace the tag** in the parse tree. |
| --- | --- |
| **`insert(position, new_element)`** | Inserts a `new_element` (tag or string) into the tag's `contents` list at a specific numerical `position`. |
| **`append(new_element)`** | Adds a `new_element` (tag or string) to the **end** of the tag's children list. |
| **`extend(list_of_elements)`** | Adds a **list of elements** to the end of the tag's children list. |



# 4. NavigableString Object

## Attributes

| Attribute | Description |
| :--- | :--- |
| **`.string`** | If a tag contains only a single text element (no nested tags), this returns the **raw string value** of that text. If the tag has multiple children, it returns `None`. |
| **`.parent`** | Returns the **parent tag**—the element immediately enclosing the current tag in the parse tree. |

## Methods

| Method | Description |
| :--- | :--- |
| **`replace_with(new_string)`** | Replaces the current `NavigableString` (text element) with the **content of `new_string`**. |


# 5. Searching the Parse Tree

Common Ways to Search:

| Method | Use Case | Example |
| :--- | :--- | :--- |
| **`find("tag")`** | Find the **first** element with the given tag name. | `soup.find("h1")` |
| **`find_all("tag")`** | Find **all** elements with the given tag name. | `soup.find_all("p")` |
| **`find(id="something")`** | Search for the first tag by its **ID attribute**. | `soup.find(id="main")` |
| **`find(class_="a")`** | Search for the first tag by its **class attribute**. (Note the trailing underscore: `class_`). | `soup.find(class_="title")` |
| **`find_all(["h1", "h2"])`** | Match **multiple** tag names at once (returns all `<h1>` and `<h2>` tags). | `soup.find_all(["h1", "h2"])` |
| **`find_all(attrs={"data-x": "123"})`** | Search for tags based on **arbitrary attributes** (e.g., custom `data-` attributes). | `soup.find_all(attrs={"data-x": "123"})` |
| **`select(".class")`** | Search using a **CSS class selector**. | `soup.select(".title")` |
| **`select("#id")`** | Search using a **CSS ID selector**. | `soup.select("#main")` |
| **`select("div > p")`** | Search using a **CSS child selector** (finds all `<p>` tags that are direct children of a `<div>`). | `soup.select("div > p")` |

# 6. Modifying the HTML Tree

| Method | Description |
| :--- | :--- |
| **`tag.append(x)`** | Adds the element or string `x` as a new **last child** of the current tag. |
| **`tag.insert(pos, x)`** | Inserts the element or string `x` into the children list at the specified numerical **position** (`pos`). |
| **`tag.extract()`** | **Removes the tag** (and all its contents) from the parse tree, but **returns the tag object**. This lets you save or reinsert the tag elsewhere. |
| **`tag.decompose()`** | **Removes and destroys the tag** (and all its contents) from the parse tree. The object is no longer usable. |
| **`tag.replace_with(x)`** | Replaces the current tag with the element or string `x` in the parse tree. Returns the tag that was replaced. |
| **`tag.clear()`** | **Removes all children and contents** from the tag, leaving the tag empty (e.g., `<div></div>`). |
| **`tag.wrap(wrapper)`** | Wraps the current tag in a new tag object called `wrapper`. The original tag becomes a child of `wrapper`. |
| **`tag.unwrap()`** | **Removes the current tag**, but keeps its children in the parse tree. The children replace the tag's position. |

# 7. Output, Formatting, Encoding

| Method | Description |
| :--- | :--- |
| **`soup.prettify()`** | Returns the entire document as a string with **nicely formatted and indented** HTML/XML output. |
| **`str(soup)`** | Returns the **raw HTML string** of the document or the specific tag. |
| **`soup.encode()`** | Converts the BeautifulSoup object (document or tag) into a **bytes object**, typically using UTF-8 encoding by default. |
| **`soup.decode()`** | Converts a bytes object back into a **string**, using the specified or detected encoding. |


----------------

# Methods With Identical `snake_case` & `CamelCase` Versions (BeautifulSoup)
`BeautifulSoup` has several pairs of methods where the CamelCase and snake_case versions are exactly the same.
This exists for backward compatibility with older BeautifulSoup versions.



BeautifulSoup provides both `snake_case` (modern/Pythonic) and `CamelCase` (legacy) versions for many of its methods. It is recommended to use the `snake_case` versions.

| `snake_case` (modern) | `CamelCase` (legacy) | Same? | Notes |
| :--- | :--- | :--- | :--- |
| **`find_all()`** | `findAll()` | **✔️ Same** | Returns a list of matching tags. |
| **`get_text()`** | `getText()` | **✔️ Same** | Extracts all text content from the element. |
| **`replace_with()`** | `replaceWith()` | **✔️ Same** | Replaces a tag with another element or string. |
| **`insert_before()`** | `insertBefore()` | **✔️ Same** | Inserts a tag or string immediately before the current tag. |
| **`insert_after()`** | `insertAfter()` | **✔️ Same** | Inserts a tag or string immediately after the current tag. |
| **`find_parents()`** | `findParents()` | **✔️ Same** | Returns all matching ancestor elements. |
| **`find_parent()`** | `findParent()` | **✔️ Same** | Returns the first matching ancestor element. |
| **`find_next_siblings()`** | `findNextSiblings()` | **✔️ Same** | Get all matching siblings that follow the current tag. |
| **`find_next_sibling()`** | `findNextSibling()` | **✔️ Same** | Get the first matching sibling that follows the current tag. |
| **`find_previous_siblings()`** | `findPreviousSiblings()` | **✔️ Same** | Get all matching siblings that precede the current tag. |
| **`find_previous_sibling()`** | `findPreviousSibling()` | **✔️ Same** | Get the first matching sibling that precedes the current tag. |
| **`find_all_next()`** | `findAllNext()` | **✔️ Same** | All elements that appear after this one in the document's parse order. |
| **`find_next()`** | `findNext()` | **✔️ Same** | The first element that appears after this one in the document's parse order. |
| **`find_all_previous()`** | `findAllPrevious()` | **✔️ Same** | All elements that appear before this one in the document's parse order. |
| **`find_previous()`** | `findPrevious()` | **✔️ Same** | The first element that appears before this one in the document's parse order. |


------

# `select()` vs `find()` / `find_all()`

## `select()` — CSS selectors

* **Syntax:** Uses **CSS selector syntax** (e.g., `.class`, `#id`, `div > p`, `ul li a`, etc.).
* **Flexibility:** It is a **very flexible and powerful** method for complex element targeting.
* **Return Type:** **Always returns a list** of matching tags (which may be empty).

```python
soup.select(".item")
soup.select("#header")
soup.select("div > p")
```

## `find()` / `find_all()` — Tag + attributes

* **Syntax:** Uses **tag names and optional attribute keyword arguments** (Python-style searching, not CSS).
* **`find()`:** Returns **one element** (the first match) or `None`.
* **`find_all()`:** Returns a **list** of all matching tags.

```python
soup.find("div", class_="item")
soup.find_all("a", href=True)
```

## When to use which?

* **Use `find()` / `find_all()` when:**
    * You know the **tag name** (e.g., `'p'`, `'div'`).
    * You know the **attributes** (e.g., `id='main'`, `class_='header'`).
    * You want a **Pythonic, structured search** using keyword arguments.
    * You want **only the first match** (`find()`).

* **Use `select()` when:**
    * You want **CSS-style queries** (familiar to front-end developers).
    * You need to match complex patterns like:
        * `div > ul > li:first-child` (Child and pseudo-class selectors)
        * `a[href*='login']` (Attribute content matching)
        * `.nav .item.active` (Multiple class matching)
    * You want **flexibility and power** for nested element relationships.
 

## `find` vs `select` — Side-by-Side Comparison

| Goal | Using `find()` / `find_all()` | Using `select()` (CSS) |
| :--- | :--- | :--- |
| **Find all `<p>` tags** | `soup.find_all("p")` | `soup.select("p")` |
| **Find all elements with class `"item"`** | `soup.find_all(class_="item")` | `soup.select(".item")` |
| **Find element with id `"header"`** | `soup.find(id="header")` | `soup.select("#header")[0]` |
| **Find all `<a>` tags with an `href` attribute** | `soup.find_all("a", href=True)` | `soup.select("a[href]")` |
| **Find all `<div>` with class `"box"` and id `"main"`** | `soup.find_all("div", class_="box", id="main")` | `soup.select("div.box#main")` |
| **Find first `<li>` inside a `<ul>`** | `soup.find("ul").find("li")` | `soup.select("ul li")[0]` |
| **Find direct child `<p>` inside `<div>`** | `soup.find("div").find("p")` | `soup.select("div > p")` |
| **Find all links containing `"login"` in `href`** | `soup.find_all("a", href=lambda x: x and "login" in x)` | `soup.select('a[href*="login"]')` |
| **Find `<span>` inside a class `"container"`** | `soup.find("div", class_="container").find_all("span")` | `soup.select(".container span")` |
| **Find siblings of an element** | `tag.find_next_siblings()` | `tag.select("~ *")` (CSS sibling) |



# Scraping tables

```python
table = soup.find("table")

rows = table.find_all("tr")[1:]

for row in rows:
    cols = row.find_all("td")

    rank = cols[0].text.strip()
    title = cols[1].text.strip()
    worldwide_gross = cols[2].text.strip()
    domestic_gross = cols[3].text.strip()
    year = cols[-1].text.strip()
```
