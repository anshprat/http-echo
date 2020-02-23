http-echo
=========
HTTP Echo is a small go web server that serves the contents it was started with
as an HTML page.

The default port is 5678, but this is configurable via the `-listen` flag:

```
http-echo -listen=:8080 -text="hello world"
```

or in docker:

```
docker run -p 8080:5678   anshprat/http-echo
```

Then visit http://localhost:8080/ in your browser.

You can pass the flags to the binary into container like:

docker run -p 8080:8888   anshprat/http-echo /http-echo -listen=:8888 -text="hello world"
