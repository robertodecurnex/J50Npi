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

## Notes

This library expect your JSON calls to accept a `callback` parameter on the url and use that function name to wrap the JSON response.

### Example

http://example.com/resource.json

    {"key":"value"}
    
http://example.com/resource.json?callback=J50Npi.success

    J50Npi.success({"key":"value"});
    
Note that you can ignore the callback param and just hardcode your responses to return this `J50Npi.success(your_json_here);` [but this is a terrible idea :P]. 
    
## Step by Step Beginner's Sample

1. Open your Browser

2. Open a non javascript intensive page; e.g. http://robertodecurnex.github.com/

3. Open the console by pressing F12 or whatever key your browser use. You may need to select tab 'Console' (tested on Chrome and Internet Explorer 10)

4. Paste the below code (within the console)

```javascript
// This line taken from J50Npi.min.js (within this repo)
var J50Npi={currentScript:null,getJSON:function(b,d,h){var g=b+(b.indexOf("?")+1?"&":"?");var c=document.getElementsByTagName("head")[0];var a=document.createElement("script");var f=[];var e="";this.success=h;d.callback="J50Npi.success";for(e in d){f.push(e+"="+encodeURIComponent(d[e]))}g+=f.join("&");a.type="text/javascript";a.src=g;if(this.currentScript){c.removeChild(currentScript)}c.appendChild(a)},success:null};

// This is a WorldIP free geo-location database.
var url = "http://api.wipmania.com/jsonp";

// No specific data need to be sent there
var data = {};

// We need a function callback to be executed after the response is received
var callback = function(geodata){ alert(geodata.address.country); };

// And here is the magic:
J50Npi.getJSON(url, data, callback);
```

You should see an alert saying your current (ip based location) country name after half a second or so.
