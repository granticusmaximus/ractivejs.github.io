# Initialisation Options

Create a new Ractive instance using the specified options. For example:

```js
ractive = new Ractive({
  el: 'container',
  template: '<p>{{greeting}}, {{recipient}}!</p>',
  data: { greeting: 'Hello', recipient: 'world' }
});
```

## Required

> ### **template** *`String` or (if [preparsing](preparsing.md)) `Array` or `Object`*
> The template to use. If this is a string, it must be valid (if meaningless, until rendered) HTML, otherwise this must be the output of [Ractive.parse()](Ractive.parse().md).
>
> Alternatively, you can pass a string like `#myTemplate` - in this case, Ractive will use the contents of an element whose ID is `myTemplate`. See the [60 second setup](http://ractivejs.org/60-second-setup) for an example of this.


## Optional

> ### el *`HTMLElement` or `String` or jQuery-like collection*
> The container element to render to, or a jQuery collection or string (see [valid selectors](valid selectors.md)).

> ### data *`Object` or `Array`*
> the data to initialise with

> ### partials *`Object`*
> a `key: value` hash of partials that are specific to this instance, where `key` is the name of the partial (as referenced within templates as `{{>myPartial}}`), and `value` is either a valid template string or the output of [Ractive.parse()](Ractive.parse().md). See [Partials](Partials.md) for more info

> ### transitions *`Object`*
> a hash of transition functions specific to this instance, referenced within templates using `intro` and `outro` attributes on elements. See [Transitions](Transitions.md) for more info

> ### complete *`Function`*
> a function that will be called when render is complete (i.e. all intro transitions have finished. If there are no intro transitions, this function will be called as soon as the instance is created)

> ### adaptors *`Array`*
> See [Adaptors](Adaptors.md)

> ### modifyArrays *`Boolean`*
> Defaults to `true`. Whether or not to modify array mutator methods to enable frictionless data binding with lists (see [array modification](array modification.md)).

> ### magic *`Boolean`*
> Defaults to `false`. Whether or not to wrap data in ES5 accessors (see [magic mode](magic mode.md)).

> ### twoway *`Boolean`*
> Defaults to `true`. Whether or not two-way data binding is enabled (see [Two‐way binding](Two‐way binding.md)).

> ### lazy *`Boolean`*
> Defaults to `false`. If two-way data binding is enabled, whether to only update data based on text inputs on `change` and `blur` events, rather than any event (such as key events) that may result in new data

> ### append *`Boolean`*
> Defaults to `false`. Whether to append the Ractive to `el`, or to overwrite the contents of `el`.

> ### computed *`Object`*
> an object that maps to a set of computed values. Refer to the documentation for examples [Computed Properties](Computed Properties.md).

> ### debug *`Boolean`*
> Defaults to `false`. Whether to print console messages to help debug applications.

> ### preserveWhitespace *`Boolean`*
> Defaults to `false`. Whether or not to preserve whitespace in templates when parsing. (Whitespace in `<pre>` elements is always preserved.)

> ### sanitize *`Boolean` or `Object`*
> Defaults to `false`. If `true`, certain elements will be stripped from templates at parse time - `<applet>`, `<base>`, `<basefont>`, `<body>`, `<frame>`, `<frameset>`, `<head>`, `<html>`, `<isindex>`, `<link>`, `<meta>`, `<noframes>`, `<noscript>`, `<object>`, `<param>`, `<script>`, `<style>` and `<title>` - as will event attributes (e.g. `onclick`). Alternatively, pass in an object with an `elements` property containing an array of blacklisted elements, and an optional `eventAttributes` boolean (`true` means 'disallow event attributes').
