<div align="center">
  <img src="https://github.com/Prozi/uwebsockets.js/raw/master/misc/logo-flat.svg" height="180" />
  
  <br/>
  
  <i>Simple, secure</i><sup><a href="https://github.com/Prozi/uwebsockets/tree/master/fuzzing#fuzz-testing-of-various-parsers-and-mocked-examples?style=flat-square">[1]</a></sup>
  <i> & standards compliant</i><sup><a href="https://unetworking.github.io/uWebSockets.js/report.pdf">[2]</a></sup>
  <i> web server for the most demanding</i><sup><a href="https://github.com/Prozi/uwebsockets/tree/master/benchmarks#benchmark-driven-development">[3]</a></sup>
  <i> of applications.</i> <a href="https://github.com/Prozi/uwebsockets/blob/master/misc/READMORE.md">Read more...</a>

<br/><br/>

<a href="https://lgtm.com/projects/g/uNetworking/uWebSockets.js/context:cpp?style=flat-square"><img alt="Language grade: C/C++" src="https://img.shields.io/lgtm/grade/cpp/g/uNetworking/uWebSockets.js.svg?logo=lgtm&logoWidth=18?style=flat-square"/></a>
<a href="https://lgtm.com/projects/g/Prozi/uwebsockets.js/context:javascript?style=flat-square"><img alt="Language grade: javascript" src="https://img.shields.io/lgtm/grade/javascript/g/Prozi/uwebsockets.js.svg?logo=lgtm&logoWidth=18?style=flat-square"/></a>
<a href="https://www.codacy.com/manual/jacekpietal/uwebsockets.js?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=Prozi/uwebsockets.js&amp;utm_campaign=Badge_Grade"><img src="https://app.codacy.com/project/badge/Grade/8b80efd8b6de4fbb837cf60ddaabc78c"/></a>
<a href="https://www.npmjs.com/package/Prozi/uwebsockets.js"><img src="https://img.shields.io/npm/v/uwebsockets.js.svg?style=flat-square" alt="npm" /></a>
<a href="https://github.com/Prozi/uwebsockets.js"><img src="https://img.shields.io/github/release/Prozi/uwebsockets.js.svg?style=flat-square" alt="release" /></a>
<a href="https://github.com/Prozi/uwebsockets.js/blob/master/LICENSE"><img src="https://img.shields.io/npm/l/uwebsockets.js.svg?style=flat-square" alt="license" /></a>
<a href="https://www.npmjs.com/package/Prozi/uwebsockets.js"><img src="https://img.shields.io/npm/dt/uwebsockets.js.svg?style=flat-square" alt="downloads" /></a>
<a href="https://david-dm.org/Prozi/uwebsockets.js"><img src="https://david-dm.org/Prozi/uwebsockets.js.svg?style=flat-square" alt="dependencies" /></a>
<a href="https://github.com/Prozi/uwebsockets.js/graphs/commit-activity"><img src="https://img.shields.io/maintenance/yes/2020.svg?style=flat-square" alt="maintained" /></a>
<a href="https://onury.io/docma"><img src="https://img.shields.io/badge/docs%20by-docma-c27cf4.svg?docs%20by=docma&style=flat-square" alt="documentation" /></a>
<a href="https://circleci.com/gh/Prozi/uwebsockets.js" alt="circleci"><img src="https://circleci.com/gh/Prozi/uwebsockets.js.svg?style=shield" alt="passing" /></a>

</div>

### 💡 Familiar face

µWebSockets.js is a C++ implementation of the Http/WebSocket protocols for Node.js, easy to use from JavaScript. Think of it as a faster Express.js/Socket.IO alternative; it comes with both router and pub/sub support. Browse this:

- [documentation](https://prozi.github.io/uwebsockets.js/)
- [api documentation](https://unetworking.github.io/uWebSockets.js/generated/)
- [main original repo](https://github.com/uNetWorking/uWebSockets)

There are tons of [examples](https://github.com/uNetworking/uWebSockets.js/tree/master/examples) but here's the gist of it all:

```javascript
/* Non-SSL is simply App() */
require("uwebsockets.js")
  .SSLApp({
    /* There are tons of SSL options */
    key_file_name: "misc/key.pem",
    cert_file_name: "misc/cert.pem",
  })
  .ws("/*", {
    /* For brevity we skip the other events */
    message: (ws, message, isBinary) => {
      let ok = ws.send(message, isBinary);
    },
  })
  .any("/*", (res, req) => {
    /* Let's deny all Http */
    res.end("Nothing to see here!");
  })
  .listen(9001, (listenSocket) => {
    if (listenSocket) {
      console.log("Listening to port 9001");
    }
  });
```

### 💪 Unfair advantage

Being written in native code directly targeting the Linux kernel makes it way faster than any JavaScript implementation:

<img src="https://github.com/Prozi/uwebsockets.js/raw/master/misc/chart.png" />

- Install with `yarn add uwebsockets.js --save`. No compiler needed.

### 💼 Commercially supported

<a href="https://github.com/uNetworking">uNetworking AB</a> is a Swedish consulting & contracting company dealing with anything related to µWebSockets; development, support and customer success.

Don't hesitate <a href="mailto:alexhultman@gmail.com">sending a mail</a> if you're building something large, in need of advice or having other business inquiries in mind. We'll figure out what's best for both parties and make sure you're not stepping into one of the many common pitfalls.

Special thanks to BitMEX, Bitfinex, Google, Coinbase, Bitwyre and deepstreamHub for allowing the project itself to thrive on GitHub since 2016 - this project would not be possible without these beautiful companies.

<img src="https://github.com/uNetworking/uWebSockets/raw/master/misc/2018.png" />

- µWebSockets.js is the Node.js binding to µWebSockets. Read more over at [µWebSockets](https://github.com/Prozi/uwebsockets).

<img src="https://github.com/Prozi/uwebsockets.js/raw/master/misc/features_strip.png" />
