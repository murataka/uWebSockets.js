<div align="center">
<img src="https://raw.githubusercontent.com/uNetworking/uWebSockets/master/misc/logo.svg" height="180" /><br>
<i>Simple, secure</i><sup><a href="https://github.com/uNetworking/uWebSockets/tree/master/fuzzing#fuzz-testing-of-various-parsers-and-mocked-examples">[1]</a></sup><i> & standards compliant</i><sup><a href="https://unetworking.github.io/uWebSockets.js/report.pdf">[2]</a></sup><i> web server for the most demanding</i><sup><a href="https://github.com/uNetworking/uWebSockets/tree/master/benchmarks#benchmark-driven-development">[3]</a></sup><i> of applications.</i> <a href="https://github.com/uNetworking/uWebSockets/blob/master/misc/READMORE.md">Read more...</a>
<br><br>


<a href="https://github.com/uNetworking/uWebSockets.js/releases"><img src="https://img.shields.io/github/v/release/uNetworking/uWebSockets.js"></a> <a href="https://lgtm.com/projects/g/uNetworking/uWebSockets.js/context:cpp"><img alt="Language grade: C/C++" src="https://img.shields.io/lgtm/grade/cpp/g/uNetworking/uWebSockets.js.svg?logo=lgtm&logoWidth=18"/></a> <img src="https://img.shields.io/badge/downloads-50,000,000+-green" />

</div>
<br><br>

### :muscle: Unfair advantage

µWebSockets.js is a C++ implementation of the Http/WebSocket protocols for Node.js, easy to use from JavaScript without the need for a compiler. Read more over at [µWebSockets](https://github.com/uNetworking/uWebSockets), the main repository.

![](misc/chart.png)

### :bulb: In a nutshell

Think of it as a complete replacement to both Express.js and Socket.IO. It carries both a router and pub/sub support. Browse the [documentation](https://unetworking.github.io/uWebSockets.js/generated/). There are tons of [examples](examples) but here's the gist of it all:

```javascript
/* Non-SSL is simply App() */
require('uWebSockets.js').SSLApp({

  /* There are tons of SSL options */
  key_file_name: 'misc/key.pem',
  cert_file_name: 'misc/cert.pem',
  
}).ws('/*', {

  /* For brevity we skip the other events */
  message: (ws, message, isBinary) => {
    let ok = ws.send(message, isBinary);
  }
  
}).any('/*', (res, req) => {

  /* Let's deny all Http */
  res.end('Nothing to see here!');
  
}).listen(9001, (listenSocket) => {

  if (listenSocket) {
    console.log('Listening to port 9001');
  }
  
});
```

### :rocket: Ready all thrusters

Install with `npm install uNetworking/uWebSockets.js#v18.1.0` or any such [release](https://github.com/uNetworking/uWebSockets.js/releases). No compiler needed.
