# spa-vertx-basic
A Basic Vert.x web application configured for a single page client application.

This was *much* easier than the corresponding SpringMVC version.

Key features:

 * The web application is mapped to the root "/" context
 * All static resources are under the "/assets/" path
 * A request for "index.html" will redirect to "/" for a nicer URL in the address bar
 * All web-service API are under an "/api/" path
 * A request for an unknown API will have a catch-all that maps to a BAD_REQUEST response
 * Any other request, including deep-link requests, will map to the single page web application for client
   routing
 * Does NOT rely on ugly hashes '#' in URLs or the address bar 

The names for the path prefixes used are arbitrary and can be changed to whatever you prefer.

Right now there is no client application integrated, this will come for ReactJS shortly and maybe AngularJS
later (I simply like React way more).

You can run this project from a shell/terminal, simply type:

```
mvn exec:java
```


Then open your browser at the following URLs to prove it's all configured properly:

```
http://localhost:8080
http://localhost:8080/index.html
http://localhost:8080/api/users
http://localhost:8080/api/users/boss
http://localhost:8080/api/users/emo
http://localhost:8080/api/users/emma
http://localhost:8080/api/version
http://localhost:8080/api/anything-else-does-not-exist
http://localhost:8080/assets/css/index.css
http://localhost:8080/assets/img/star.png
http://localhost:8080/assets/js/app.js
```

It can still be useful to route to static assets on the server - e.g. images or scripts that not part of the client
application itself.

This project also has client-side routing enabled. These are deep links that will be routed to the client index
page where the React router will take over:

```
http://localhost:8080/users
http://localhost:8080/users/boss
http://localhost:8080/users/emo
http://localhost:8080/users/emma
http://localhost:8080/a/not/found/page
```

Full refreshes will work and be routed correctly.

Your single page web application would be expected to be published at "WEB-INF/assets/index.html".

Looking for a working ReactJS version of this project, here you are [spa-vertx-react](https://github.com/caprica/spa-vertx-react).

You're welcome.
