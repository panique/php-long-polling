# php-long-polling

A very simple demonstration of long-polling with AJAX (jQuery) and PHP. Long-polling makes near "real-time"
applications possible. The client does not request new data every X seconds/minutes, the client gets new data
delivered when there is new data (push-notification style). This is an improved, cleaned and documented
fork of https://github.com/lincolnbrito/php-ajax-long-polling ! Big thanks, man.

## What is long-polling (and short polling) ?

#### Short-polling

Send a request to the server, get an instant answer. Do this every x seconds, minutes etc. to keep your application
up-to-date. But: This costs a lot of requests.

#### Long-polling

Send a request to the server, keep the connection open, get an answer when there's "data" for you. This will cost you
only one request (per user), but the request keeps a permanent connection between client and server up.

## How to use

To test, simply change the URL in client/client.js to the location of your server.php file, for local testing
`url: 'http://127.0.0.1/php-long-polling/server/server.php'` will do the job. Open the `client/index.html` to simulate
the client.

While having the index.html opened in your browser, edit the data.txt on the server (and save it). You'll see index.html
instantly (!) getting the new content. Voila!

You should get a good idea how everything works by looking into the code, I think it's self-explaining.

## In a real-world application ...

This would work perfectly in a real-world application, BUT

1. There are better tools for this, like node.js, which can handle MUCH more concurrent connections and serve
data faster, with much less memory usage and afaik while using only ONE thread.

2. Apache2 uses 18MB afaik per thread by default, so having a "permanent connection" with 100 clients will use a lot
of memory. I'm currently experimenting with lighttpd, NGINX and appserver.io to find a better solution.

## You like that ?

:) Then have a look at my blog [DEV METAL](http://www.dev-metal.com), at [my other repos](https://github.com/panique) or support this and other projects by renting a server at [Host1Plus](https://affiliates.host1plus.com/ref/devmetal/36f4d828.html). Thanks!
