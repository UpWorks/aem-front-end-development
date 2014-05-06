HandleBarsJS
============

Handlebars templates look like regular HTML, with embedded handlebars expressions.

````
<div class="entry">
  <h1>{{title}}</h1>
  <div class="body">
    {{body}}
  </div>
</div>
````
A handlebars expression is a `{{, some contents, followed by a }}`

You can deliver a template to the browser by including it in a `<script>` tag.
````
<script id="ima-template" type="text/x-handlebars-template">
  <div class="entry">
  <h1>{{title}}</h1>
  <div class="body">
    {{body}}
  </div>
</div>
</script>
````
Compile a template in JavaScript by using Handlebars.compile
````
var source   = $("#ima-template").html();
var template = Handlebars.compile(source);
````
It is also possible to pre-compile your templates. This will result in a smaller required runtime library and significant savings from not having to compile the template in the browser. This can be especially important when working with mobile devices.

Next, get the HTML result of evaluating a Handlebars template by executing the template with a context.
````
var context = {title: "My New Post", body: "This is my first post!"}
var html    = template(context);
````
results in
````
<div class="entry">
  <h1>My New Post</h1>
  <div class="body">
    This is my first post!
  </div>
</div>
````
Now lets take a look at how we use HandleBar templates for our modal and used lazy loading when the modal is activated.
