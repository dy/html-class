# html-class [![build status](https://secure.travis-ci.org/WebReflection/html-class.svg)](http://travis-ci.org/WebReflection/html-class)
A basic utility to retrieve a DOM node name from its constructor and vice-versa.

```js
// grab the module
const htmlClass = require('html-class');

// logs: HTMLAnchorElement
htmlClass.get('a');

// logs: p
htmlClass.get('HTMLParagraphElement');

// define custom elements (tag, Class) or (Class, tag)
htmlClass.set('MyEl', 'my-el');
htmlClass.set('my-other', 'MyOther');
```

The API right now is literally just a `.get(tagOrClass)` and a `.set(tag, Class)` that also works as `.set(Class, tag)`.

As special feature, `.get(regExp)` returns an array of known classes or elements that match the regular expression.

```js
// returns ['HTMLButtonElement']
htmlClass.get(/^HTMLButton/);

// returns all known/registered custom elements
// ['my-el', 'x-form', 'some-data']
htmlClass.get(/\w-/);
```

The code is compatible with every JavaScript engine, either browsers or servers.
