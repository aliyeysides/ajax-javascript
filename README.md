ajax-javascript
===============

Simple, lightwight and easy to use ajax function in pure javascript

This function is written in pure javascript only. No jQuery or other dependencies.<br/>
I expect that this is gonna help you to do your job easily if you want ajax without jQuery.<br/>
There are various options you can take. POST or GET method, using predefined callback function, passing function body in the middle of the parameters and even jsonp option.

<h2>Installation</h2>
Simple! Just include ajax-javascript.js file somewhere.
```html
<script src="/path/to/ajax-javascript.js"></script>
```
<h2>Useage</h2>
<h3>Communicating with local web API</h3>
<h4>GET request</h4>
```javascript
ajax( "/path/to/api.json" );
```
<h4>GET request with parameters</h4>
```javascript
ajax( "/path/to/api.json" , { data : { p_name : "name" , variable : 1234 } } );
```
<h4>POST request</h4>
```javascript
ajax( "/path/to/api.json" , { isPost : true } );
```
<h4>POST request with parameters</h4>
```javascript
ajax( "/path/to/api.json" , {
	isPost : true ,
	data : { p_name : "name" , variable : 1234 }
});
```
<h4>Using predefined function as callback</h4>
```javascript
function callbackFunctionName ( data )
{
	// code here
}

ajax( "/path/to/api.json" , {
	isPost : true ,
	callback : "callbackFunctionName" ,
	data : { /* data object here */ }
});
```
<h4>Setting callback function</h4>
```javascript
ajax( "/path/to/api.json" , {
	isPost : true ,
	callback : function( data ) {
		// code here
	} ,
	data : { /* data object here */ }
});
```
<h3>JSONP Communication</h3>
<h4>Using predefined function as callback</h4>
```javascript
function callbackFunctionName ( data )
{
	// code here
}

ajax( "http://www.example.com/path/to/api.json" , {
	jsonp : true ,
	callback : "callbackFunctionName" ,
	data : { /* data object here */ }
});
```
<h4>Setting callback function</h4>
```javascript
ajax( "http://www.example.com/path/to/api.json" , {
	jsonp : true ,
	callback : function( data ) {
		// code here
	} ,
	data : { /* data object here */ }
});
```
<h2>Options</h2>
<h3>CallBack</h3>
<h4>Callback with name</h4>
```javascript
callback : "CallbackFunctionName"
```
Defines callback function with predefined function name. You can set any function in the document as callback function. That function will be executed when your broswer received response data from the server.
<h4>Callback with function element</h4>
```javascript
callback : function( data ){
	// code here
};
```
You can define callback function within the option parameter. If you are lazy and you just wanna pass your callback function directly, just giving your callback function like above.
<h3>Data</h3>
```javascript
// data must be object element(not array)
data : { /* data object here */ }
```
Sets variables to be sent
<h3>Cross Domain</h3>
```javascript
jsonp : true
```
You can also make a cross domain request. Simply set jsonp option to true and ajax function will do the script injection for you. Make sure your remote server is safe
<h3>Post</h3>
```javascript
// Default is false (GET)
isPost : true // POST
isPost : false // GET
```
Default is GET. In order to send POST request, you can simply set isPost option to true.
<h2>Author</h2>
https://www.linkedin.com/in/samma
