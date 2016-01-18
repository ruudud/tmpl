# tmple
Fork of [jasonmoo/t.js](https://github.com/jasonmoo/t.js) with CommonJS support
and improved HTML sanitation based on [OWASP][] recommendations. 


## Idea
Focus on making it easy to do simple (yet common!) tasks like if-checks and
simple loops, but making it hard to do a lot of logic inside template.

In addition, the size of the library itself should be as tiny as possible for
use in browsers.


## Features
 * Simple interpolation: `{{=value}}`
 * Scrubbed interpolation: `{{%unsafe_value}}`
 * Name-spaced variables: `{{=User.address.city}}`
 * If/else blocks: `{{value}} <<markup>> {{:value}} <<alternate markup>> {{/value}}`
 * If not blocks: `{{!value}} <<markup>> {{/!value}}`
 * Object/Array iteration: `{{@object_value}} {{=_key}}:{{=_val}} {{/@object_value}}`
 * Multi-line templates (no removal of newlines required to render)
 * Render the same template multiple times with different data
 * Works in all modern browsers


## Using
This module supports CommonJS (Node and Browserify with
[tmple transform](https://github.com/ruudud/tmpleify)), AMD (RequireJS) and
VanillaJS.

```
var template = new tmple("<div>Hello {{%name}}</div>");
document.body.innerHtml = template.render({name: "World!"});
```

For more advanced usage, check 
[`tmple_test.html`](https://github.com/ruudud/tmple/blob/master/tmple_test.html).


## License
MIT


[OWASP]: https://www.owasp.org/index.php/XSS_(Cross_Site_Scripting)_Prevention_Cheat_Sheet#RULE_.231_-_HTML_Escape_Before_Inserting_Untrusted_Data_into_HTML_Element_Content
