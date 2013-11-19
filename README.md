# php-long-polling

A very simple demonstration of long-polling with AJAX (jQuery) and PHP. Long-polling makes near "real-time"
applications possible. The client don't request new data, the client gets new data delivered (push-notification style).
This is an improved, cleaned and documented fork of https://github.com/lincolnbrito/php-ajax-long-polling !
Big thanks, man.

## What is long-polling (and short polling) ?

#### Short-polling

Send a request to the server, get an instant answer. Do this every x seconds, minutes etc.

#### Long-polling

Send a request to the server, keep the connection open, get an answer when there's "data" for you.

## How to use

To test, simply change the URL in client/client.js to the location of your server.php file:
`url: 'http://127.0.0.1/php-long-polling/server/server.php'` and open the client/index.html.
You should get a good idea how everything works by looking into the code, I think it's self-explaining ;)

## In a real-world application ...

This would work perfectly in a real-world application, BUT

1. There are better tools for this, like node.js, which can handle MUCH more concurrent connections and serve
data faster, with much less memory usage and afaik while using only ONE thread.

2. Apache2 uses 18MB afaik per thread by default, so having a "permanent connection" with 100 clients will use a lot
of memory. I'm currently experimenting with lighttpd, NGINX and appserver.io to find a better solution.
