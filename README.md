# J50Nπ

Basic JSONP helper (pure JS)

## Authors

Roberto Decurnex (nex.development@gmail.com)

## Download

You clone the project with Git by running:

    $ git clone git://github.com/robertodecurnex/J50Npi

## Quick Sample

```javascript
var url = "http://domain/something.jsonp";
var data = {};
var callback = function(data){ alert(data.attribute_name)};

J50Npi.getJSON(url, data, callback);
```

Note that the given url does not need a callback parameter. It will be set automatically to **J50Npi.success** that will be the one executing the given callback function.
