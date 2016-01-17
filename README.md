# tmpl
Fork of [jasonmoo/t.js](https://github.com/jasonmoo/t.js) with CommonJS support
and improved HTML sanitation based on [OWASP][] recommendations. 


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

```
var template = new tmpl("<div>Hello {{%name}}</div>");
document.body.innerHtml = template.render({name: "World!"});
```

For more advanced usage, check the
[`tmpl_test.html`](https://github.com/ruudud/tmpl/blob/master/tmpl_test.html).


## Browserify transform
Checkout [ruudud/tmplify](https://github.com/ruudud/tmplify) for a simple
transform to use with Browserify.


## License
MIT


[OWASP]: https://www.owasp.org/index.php/XSS_(Cross_Site_Scripting)_Prevention_Cheat_Sheet#RULE_.231_-_HTML_Escape_Before_Inserting_Untrusted_Data_into_HTML_Element_Content
