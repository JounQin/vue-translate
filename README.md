# Vue Translate

A translator directive for Vue.


## The Basics

```js
var Vue = require('Vue');
var translate = require('vue-translate');
Vue.use(translate);

// the messages data
translate.messages = {
  "hello": "你好"
};
```

## Use as directive

The `v-trans` directive will translate `title`, `arial-label`, `alt` and text content
automaticly.

```html
<div v-trans title="hello">hello</div>

<!-- will be translated to -->
<div title="你好">你好</div>
```

### Translate more attributes

If the message you want to translate is not on the default attributes, e.g. `data-message`,
you can pass it to `v-trans`.

```html
<div v-trans="data-message" data-message="hello">hello</div>

<!-- will be translated to -->
<div data-message="你好">你好</div>
```

### Translate with variables

The translation messages can contain variables:

```js
translate.messages = {
  "hello {{ name }}": "你好 {{ name }}"
};
```

If `{{ name }}` is `lepture`:

```html
<div v-trans>hello {{ name }}</div>

<!-- will be translated to -->
<div>你好 lepture</div>
```
