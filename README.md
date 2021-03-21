# Waitbutwhy.com to Instapaper.com

Please read here for what is it all about:
http://tordans.github.io/waitbutwhy-to-instapaper/

# How to add posts

1. Copy the JS below in your Google Chrome Console
2. Create a new html file, use the copy-paste filename and content
3. Add the artikel to the index.html
4. Create a pull request for it all

## Copy Paste JS

```javascript
// The title of our new html file
title = 'waitbutwhy.com: ' + $('.entry-header').text();
// Remove social sharing that we cannot use in instapaper
$('.homeSocial').remove();
$('#socBarmageddon').remove();
$('#social-ads').remove();
// Extend the body so the footnotes become part of the article
$('a.footnote-button').after("<br><em>[FOOTNOTE-START:]</em> "+$('a.footnote-button').attr('data-footnote-content')+" <em>[/FOOTNOTE-END]</em><br>")
// The body of our new html file
body = $('.post');
url_readable = window.location.hostname+window.location.pathname;
replace_urles = new RegExp('/', 'g');
url_as_filename = url_readable.replace(replace_urles, '_');
copy_paste_me = "\n\n<!-- FILENAME: "+url_as_filename+" -->\n\n<head><meta name='robots' content='noindex'><title>"+title+"</title><meta content='text/html; charset=utf-8' http-equiv='Content-Type' /><meta name='robots' content='noindex'></head><body><h1>Find the original content here: <a href='"+window.location.href+"'>"+url_readable+"</a></h1><hr>"+body.html()+"</body></html>\n\n";
console.log('--- COPY PAST THIS: ---');
copy_paste_me;
```
