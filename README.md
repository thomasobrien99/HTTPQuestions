## HTTP Questions

__URLs__

* Name all of the parts of the url that you can remember.  In your own words describe what they do.


  * protocol
    * The protocol is the set of rules that browsers and servers use to communicate back and forth. HTTP(S) is the standard protocol and is almost universal.
    
  * domain
    * The domain is what we typically think of as the name for a webpage, such as www.google.com. They are used to identify one or more IP addresses.
    
  * port
    * A port is an endpoint of communication. Typically they are left out of urls, and are thus set as a default( 443 for HTTPS and 80 for HTTP). "It indicates the technical "gate" used to access the resources on the web server." (https://developer.mozilla.org/en-US/Learn/Common_questions/What_is_a_URL)
    
  * path
    * The path is the actual file path on the server.
     
  * query string
    * A query is commonly found in the URL of dynamic pages (ones which are generated from database or user-generated content) and is represented by a question mark followed by one or more parameters. The query directly follows the domain name, path or port number.
    
   * anchor
     * An anchor usually appears at the end of a URL and is identified with a # character. It refers to a section within a web page.         
   
* Name the pieces of the following urls:
	* `https://www.google.com/`
	  * "https://" - the "protocol"
	  * "www.google.com" - the "domain"
	  
	* `https://workbook.galvanize.com/cohorts/41/learning_experiences/367`
		  * "https://" - the "protocol"
	      * "workbook.galvanize.com" - the "domain"
	
	* `http://locahost:5000/animals/puppies?onlycute=1&size=medium#firstpuppy`
		  * "http://" - the "protocol"
	      * "localhost" - the "domain"
	      * ':5000' - the "port"
	      * '/animals/puppies' - the "path"
	      * '?onlycute=1&size=medium' - the "query string"
	      * '#firstpuppy' - the "anchor"
	
	* `https://en.wikipedia.org/wiki/List_of_HTTP_status_codes#4xx_Client_Error`
		  * "https://" - the "protocol"
	      * "en.wikipedia.org" - the "domain"
	      * "wiki/List_of_HTTP_status_codes" - the "path"
	      * "#4xx_Client_Error" - the "anchor"
	      
* Can a server use more than 1 port?
 
```
Yes it can.

```
 
* Why is https different than http?

```
HTTP requests are not encrypted, while HTTPS requests are. HTTPS uses port 443 and TSL (Transport Security Layer) to encrypt data sent via HTTPS
```


* How does a server interpret the following url's query parameter.  What data structure does it create on the server?

```
http://locahost:5000/animals?puppies=fido&puppies=max&puppies=moxie
```


__HTTP Request/Response__

* Name at least 4 http verbs

```
GET, DELETE, POST, PUT
```

* What is each verb useful for in your own words

```
GET - Useful for requesting information from a server. Nothing on the server's state is changed.
DELETE - Useful for removing information from a server.
POST - Useful for adding information to a server.
PUT - Useful for updating existing information on a server.
```

* What does idempotent mean?

```
If a request is idempotent, it does not change any state on the server
```


* Name the 5 http status code ranges.  What are they used for in general?

```
100 - In process
200 - Status ok
300 - Redirect
400 - Client-side error
500 - Server-side error
```

* If a server returns a http status code of 301 and a location of `https://www.google.com/`, what does the browser do?

```
Redirects the client to www.google.com.
```

* For the following HTTP headers, decide if the following header is used for requests, responses or both:
	* Accept
	
	```
	Both
	```
	
	* Content-type
	
	```
	Both
	```
	
	* User-agent
	
	```
	Requests
	```
	
	* Set-cookies
	
	```
	Responses
	```
	
	* Cache-control
	
	```
	Requests
	```
	
	* Cookie
	
	```
	Requests
	```
	
* Is the following a http request or response?  How do you know for each?

```
HTTP/1.1 200 OK
Access-Control-Allow-Origin: *
Vary: Accept
Content-Type: text/html; charset=utf-8
Content-Length: 722
ETag: W/"2d2-Wu0We9N5g35FXWY+gOATLA"
Date: Tue, 08 Mar 2016 20:37:11 GMT
Connection: keep-alive

<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <link rel="stylesheet" href="/style.css">
    <title>Student Roster</title>
  </head>
  <body>
    <main>
      <h1>Student Roster</h1>
      
        <section>
          <h3>Daenerys Targaryen</h3>
          <span>Student Id: nys8fbohl</span>
          <h4>Hobby: Motherhood</h4>
          <img src="https://i.imgur.com/KlycRG5.jpg" alt="Daenerys Targaryen" />
        </section>
      
        <section>
          <h3>Tyrion Lannister</h3>
          <span>Student Id: njehukbohe</span>
          <h4>Hobby: Traveling</h4>
          <img src="https://i.imgur.com/fFMusdC.png" alt="Tyrion Lannister" />
        </section>
      
    </main>
  </body>
</html>

```
```
A response. This is what the server sends to the client upon a get request for an HTML file. The status code at the top is an indicator.
```

```
DELETE /students/n1vmyrw3x HTTP/1.1
Host: g22-students.herokuapp.com
Accept: application/json
Cache-Control: no-cache
Postman-Token: 0041e3c3-efdb-f0c3-b2f4-2d79f6d0f44b
```

```
A request. The 'verb' at the top is an indicator. The client is requesting that the server delete some data.
```


__JSON__

* Describe what JSON is.  What is it used for?

```
JSON stands for JavaScript Object Notation. It is used for sending data to be parsed into javascript by either the server or the client. The text is similar in appearance to objects in JS, but it is all in string form ("stringified"). It needs to be parsed in order to be useful for the program.

```

* Convert the following map into a javascript object then console log the age.

```
{ "company" : "Github", "age": 7, "categories" : "Services,Internet,Software"}
```

```
var jObj = JSON.parse('{ "company" : "Github", "age": 7, "categories" : "Services,Internet,Software"}');
console.log(jObj.age);
```

* Convert the following to a javascript object.  Console log each company name.

```
{ "Companies":[ { "company": "Github", "age": 7, "categories": "Services,Internet,Software"},
              { "company": "Airbnb", "age": 6, "categories": "Hotels,Travel"},
              { "company": "Square", "age": 7, "categories": "FinTech,Hardware + Software,Finance"},
              { "company": "Dropbox", "age": 11, "categories": "Cloud Data Services,Storage,Web Hosting"}
            ]
}
```

```
var jObj = JSON.parse('{ "Companies":[ { "company": "Github", "age": 7, "categories": "Services,Internet,Software"}, { "company": "Airbnb", "age": 6, "categories": "Hotels,Travel"}, { "company": "Square", "age": 7, "categories": "FinTech,Hardware + Software,Finance"}, { "company": "Dropbox", "age": 11, "categories": "Cloud Data Services,Storage,Web Hosting"}]}');

var companyNames = jObj.Companies.map(function(el){return el.company});

companyNames.forEach(function(e){console.log(e)});
```

* The following is javascript.  Convert the object to a string and console log it.

```
var myObj = {
  company: "Galvanize",
  age: 3,
  categories: "Education"
};
```

```
var str = JSON.stringify(myObj);
console.log(str);
```


__MISC__

* Describe what DNS is.

```
The "Domain Name System" - is a scheme for giving a name to any resources on the internet. We use it to translate more human-readable and memorable names to IP addresses.
```

* In the terminal, type `man curl`.  Look at the man page for curl.  What do the following flags do? `-v`, `-X`.  (Hint: to search for a string, type `/` then the text you want, then enter.  To quit the man page, type `q`).

```
-v, similarly to other -v flags, -v in this context gives a more "verbose" return message.
-X, creates a new custom request method ("verb"). This flag is not usually needed, but can used to use DELETE or other HTTP requests.
```

* What is TCP/IP?  How does it interact with HTTP?

```
TCP/IP is the fundamental transport language of the internet. TCP handles things like resending failed transmissions and breaking down big chunks of data. HTTP is a higher level protocol that uses TCP/IP to use the internet. IP is a scheme for providing addresses for every device connected to the the internet. It is to these addresses that packets of data are routed.
```


* Does HTTP break the data that is being sent into small packets?  If not, what protocol is responsible for it?

```
It does not. TCP is responsible for breaking down bigger chunks of data.
```
