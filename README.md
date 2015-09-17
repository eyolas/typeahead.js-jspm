# typeahead.js-jspm

Make using [typeahead.js](http://twitter.github.io/typeahead.js/) with jspm a little easier. 

The standard `typeahead.js` npm package doesn't expose Bloodhound, and loads it's jQuery plugin as soon as it's required. 

This package is just a small wrapper that allows you to access Bloodhound and load the jQuery plugin explicitly. 

# Usage

Bloodhound: 
```javascript
import {Bloodhound} from "typeahead.js-jspm";
var engine = new Bloodhound({
  local: ['dog', 'pig', 'moose'],
  queryTokenizer: Bloodhound.tokenizers.whitespace,
  datumTokenizer: Bloodhound.tokenizers.whitespace
});
```

For jQuery just `import` jquery, and then call `loadjQueryPlugin()`. typeahead.js will attach itself to the previously required jQuery.

```javascript
import $ from "jquery";
import typeahead from "typeahead.js-jspm";
typeahead.loadjQueryPlugin();
```