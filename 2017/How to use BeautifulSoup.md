# Writing At First
I think BeautifulSoup is easy to be used. And I will just say a little things about it.
# Install
```
pip install beautifulsoup4
```
# Using
```
soup = BeautifulSoup(html) # input a html and its type is string.
```
or
```
soup = BeautifulSoup(open(file))
```
is OK.

Then `soup.prettify()` can get a pretty string

Then `soup.title` can get its `title` tag.

`soup.head` can get its `head` tag.

`soup.a` can get its `a` tags.

`soup.p` can get its `p` tags.

Both of them are Tag class.

What I use is `soup.find_all()`.

```
find_all( name , attrs , recursive , text , **kwargs )
```
This function can find all the tags which named what you input.

You can input a string or a function or a regular expression even a boolean.
