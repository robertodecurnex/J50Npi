<h1>J50Nπ</h1>
<p>Basic JSONP helper (pure JS)</p>

<h2>Authors</h2>

Roberto Decurnex (nex.development@gmail.com)

<h2>Download</h2>
<p>
  You clone the project with Git by running:
  <pre>$ git clone git://github.com/robertodecurnex/J50Npi</pre>
</p>

<h2>Quick Sample</h2>
<p>
  <pre>var url = "http://domain/something.jsonp";  
var data = {};  
var callback = function(data){ alert(data.attribute_name)};

J50Npi.getJSON(url, data, callback);</pre>
  Note that the given url does not need a callback parameter. It will be set automatically to <b>J50Npi.sucess</b> that will be the one executing the given callback function.
</p>

