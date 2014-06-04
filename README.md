ajax-javascript
===============

Simple, lightwight and easy to use ajax function in pure javascript
<p>
This function is written in pure javascript only. No jQuery or other dependencies.
I expect that this is gonna help you to do your job easily if you want ajax without jQuery.
</p>
<h2>Installation</h2>
<p>Simple! Just include ajax-javascript.js file somewhere.</p>
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
<p>Defines callback function with predefined function name</p>
<h4>Callback with function element</h4>
```javascript
callback : function( data ){
	// code here
};
```
<p>You can define callback function within the option parameter</p>
<h3>Data</h3>
```javascript
// data must be object element(not array)
data : { /* data object here */ }
```
<p>Sets variables to be sent</p>
<h3>Cross Domain</h3>
```javascript
jsonp : true
```
<p>You can also make a cross domain request. Simply set jsonp to true and ajax function will do the script injection for you</p>
<h3>Post</h3>
```javascript
// Default is false (GET)
isPost : true // POST
isPost : false // GET
```
<p>Default is GET. In order to send POST request, you can simply set isPost option to true.</p>
<h2>Author</h2>
<p>https://www.linkedin.com/in/samma</p>
