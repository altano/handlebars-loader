# handlebars-loader

A [`handlebars`](http://handlebarsjs.com) template loader for [`webpack`](https://github.com/webpack/webpack).

## General Usage

### webpack configuration

``` javascript
{
  ...
  module: {
    loaders: [
      ...
      { test: /\.handlebars$/, loader: "handlebars" }
    ]
  }
}
```

### Your JS making use of the templates

``` javascript
var template = require("./file.handlebars");
// => returns file.handlebars content as template function
```

## Details

The loader resolves partials and helpers automatically. They are looked up relative to the current directory, or as module if you prefix `~`.

``` handlebars
A file "/folder/file.handlebars".
{{> partial}} will reference "/folder/partial.handlebars".
{{> ../partial}} will reference "/partial.handlebars".
{{> ~module/partial}} will reference "/folder/node_modules/module/partial.handlebars".
{{helper}} will reference the helper "/folder/helper.js" if this file exists.
{{../helper}} {{~module/helper}} similar to partials.
```

See [`webpack`](https://github.com/webpack/webpack) documentation for more information regarding loaders.

## Full example

See example folder in this repo.

## License

MIT (http://www.opensource.org/licenses/mit-license)