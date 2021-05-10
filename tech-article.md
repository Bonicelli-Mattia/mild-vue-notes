# PUBLISHED AT
[Dev to](https://dev.to/bonicellimattia/build-a-nodejs-server-without-using-express-52ed)








Ever wondered how to build a server without using express?

Well, look no further...
&nbsp;
&nbsp;
## Introduction
&nbsp;
While a very convenient framework express is not necessary to get up and running with a server built on nodeJS.

[Looking at how express operates](https://github.com/expressjs/express/blob/master/lib/application.js) you'll realize that under the hood it utilizes the **http** module, and as such you can think of express as a wrapper for http.

With this in mind we shall attempt to spin up a server using the http module alone.
&nbsp;
&nbsp;
## Getting started
&nbsp;
The amount of code we need to write to achieve this is minimal.

```javascript
const http = require('http');

const requestListener = function (req, res) {
  res.writeHead(200);
  res.end("I'm a server");
}

const server = http.createServer(requestListener);
server.listen(8080);
```

Yep, that's all you need.

Assuming you name this file server.js all you need to do is run `node server.js` and go to `http://localhost:8080/` and you will be greeted by this.

![ksnip_20210510-045312](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/hntqx0309mx1twu7kuxh.png)

You may notice that the code to achieve this looks eerily similar to how you would do it with express...that's no coincidence.

This really reinforces the concept that Express really is just a functional layer built on top of the http module.
&nbsp;
&nbsp;
## Dissecting the code
&nbsp;
Let's take a closer look at what we've written.

```javascript
const http = require('http');
```
First we require, the http module so that we may use it, this should be already provided with most nodeJS installations so you should need to worry about installing it yourself.

```javascript
const requestListener = function (req, res) {
      ⋮
}
```
We then make a function called requestListener and expect it to take two arguments, a req (short for request) object and a res (short for response) object.

In this simple scenario we don't do anything with the request object.

```javascript
  res.writeHead(200);
```
In the response object that we send back we have a header containing the http status code 200, which marks a successful request.


```javascript
  res.end('Hello, World!');
```
When we end the request we also send back a text body containing our message.

```javascript
const server = http.createServer(requestListener);
```
After this we create a server that calls requestListener when a request is received.

```javascript
server.listen(8080);
```
And finally we tell our server to listen to port 8080 of our localhost for requests.
&nbsp;
&nbsp;
## Summary
&nbsp;
At the end of the day if you are just trying to build something simple, using express is not a necessity and you can achieve the same basic functionality by utilizing the http module.

If however you're building an API server or an app that has a database and some complexity to it, you'd likely benefit from the abstractions and quality of life improvements that express brings to the table.