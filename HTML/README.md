## HTML Questions:
==========

#### What's a `doctype` do?
it is an instruction to the web browser about what version of HTML the page is written in. meaning what feature is supported or not.

browsers use a DOCTYPE in the beginning of the document to decide whether to handle it in quirks mode or standards mode.

#### What's the difference between standards mode and quirks mode?
broswer in standards mode behaved as descipted in stand HTML CSS specification
broswer in quirks mode will violate stand specification to keep some old site from break. 

#### What are the limitations when serving XHTML pages?
New HTML5 features like audio/video native support, local storage, location. 
IE does not support XHTML

#### Are there any problems with serving pages as application/xhtml+xml?
cause Internet Explorer 8 to show a download dialog box for an unknown format instead of displaying your page, as the first version of Internet Explorer with support for XHTML is Internet Explorer 9.
> https://developer.mozilla.org/en-US/docs/Quirks_Mode_and_Standards_Mode?redirectlocale=en-US&redirectslug=Mozilla%27s_Quirks_Mode


#### How do you serve a page with content in multiple languages?
to suppor multi language, use <meta charset="utf-8">
to indicate what language used in a page, use `lang` attr on tag.

#### What kind of things must you be wary of when design or developing for multilingual sites?

#### What are data- attributes good for?
data can be stored on markups that not visible to end users, also not violating the standard HTML5.
JavaScript can easily access by `dataset`.

#### Consider HTML5 as an open web platform. What are the building blocks of HTML5?
The main building blocks are centred on HTML 5, CSS3, Javascript and SVG. Where HTML is a language to define the mark-up of a document (titles, headers, body, footer, tables, input forms etc.), CSS is a language to define style (formatting, colours, shades and the like). Javascript is a programming/scripting language and SVG is a language for creating 2D scalable vector graphics and images.
> http://yucianga.info/?p=655

#### Describe the difference between cookies, sessionStorage and localStorage.
They are all storage on the client side.
cookies is small piece of key-value pair with a expire time.
sessionStorage is on persistent and scope only to current windows.
localStorage is persisitent and socop only to domain, by key-value pair or SQL database (Web SQL)

#### Can you explain the difference between GET and POST?
They are two types of HTTP requests.
GET represents a specific resource. Should not have and side effert like insert/update because they may be requested by robots. GET use url the send data. AJAX GET in IE will be cached, so to ensure data updates, beter add a timestamp

POST represent actions on resources, like insert/update/delete. They usually sent from HTML form. Lareg data could be sent by POST. Data is send along with HTTP header, instead of data of GET in the URL.

> http://stackoverflow.com/questions/3477333/what-is-the-difference-between-post-and-get

### Make website faster

