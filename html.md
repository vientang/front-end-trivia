#HTML

####What does a doctype do? 
The doctype declaration is an instruction to the web browser about what version of the markup language the page is written in. It should be the very first thing in an HTML document, before the HTML tag. While it may look like it, is not an HTML tag.

####What's the difference between HTML and XHTML?
XHTML is HTML with a stricter markup. It provides more precise standards and specifications for how a site’s data is broken down and transmitted and therefore solved some cross-browser compatibility issues. Then HTML5 came along and pretty much squashed XHTML.

As [Will Dean](http://stackoverflow.com/users/987/will-dean) on Stack Overflow put:
> At one time, people hoped that the solution to the mess of the late 90s web markup was to persuade everyone to write XHTML rather than HTML, perhaps in the hope that the enforced discipline would transform all those polo-necked frameless-spectacle wearing graphic designers into computer programmers. Alas, there was not actually much demonstrable benefit to all this exhausting prostration at the altar of the XHTML validator, so XHTML is now out of fashion and HTML is back in.

####How do you serve a page with content in multiple languages?
The HTTP Content-Language header can be used to provide metadata about the intended audience of the page. Set your server to send the information in the HTTP Content-Language header as `Content-Language: en, hi, pa`. Also, it's good practice use a language attribute on the html tag to declare the default language of the actual text in the page - for example: `<html lang="en">` is intended for English readers.

####What kind of things must you be wary of when design or developing for multilingual sites?
Things to think about for internationalization: How users be directed to their language (e.g IP-based re-routing, UI, urls), colors, restrictive character counts, text in images might not scale properly, etc.

####What’s the data attribute used for?
Out of the box, there are a gang full of HTML5 attributes at your disposal. See the full list [here](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes). If you need an attribute that isn’t on that list, slap on a data-whatever-you-want and you’ll have your own custom attribute. Here’s an example from [MDN](https://developer.mozilla.org/en-US/docs/Learn/HTML/Howto/Use_data_attributes):
```
<article
  id="electriccars"
  data-columns="3"
  data-index-number="12314"
  data-parent="cars"
  data-role="web">
...
</article>
```
This is helpful when we want to search or filter an element by the data type using their values, or for styling, or for performance by assigning values in the markup that doesn't need to come from the server. 

####Describe the difference between a cookie, sessionStorage and localStorage. Different types of storage on the client side.
**Cookies** - Small pieces of data that is stored in key-value pairs that lets a site keep track of your movements within the site. It typically comes with an expiration time. **sessionStorage** - Data that is persisted and scoped to the current window or tab. If your window or tab is closed, the data is gone. **localStorage** - Data that is persisted and scoped to a domain by key-value pairs. localStorage data is stored in the users browser in their computer. 

Benefits of using client-side storage. 
1. Your app can work when the user is offline and maybe sync data when they're back online. 
2. It's a performance booster. You can show a large amount of data as soon as the user clicks on to your site because the data was cached locally - instead of waiting for stuff to download again. 
3. No server required. Easy peasy.

*Note: localStorage should be used for non-critical data, like data you'd store in a cache, not an actual database*
