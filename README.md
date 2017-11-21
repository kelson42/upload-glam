This Docker image allows to create a web server which offer two accesses to the content:
* One read-only at / (via HTTP)
* One read/write at /write/ (via WebDAV)

To create a container and run it:
```
$ docker run --name webdav -p 80:80 -v /media_host:/media -e USERNAME=web -e PASSWORD=dav -d kelson42/upload-glam
```

This will start a HTTP/WebDAV server listening on the default port of
80. You can access it at `http://<HOST>:80` in a browser. To access
the WebDAV acces it (via a WebDAV ready client) at
`dav://<HOST>/write`. This server will serve files located in your
/media_host directory on you Docker hosting system. In the command
above the WebDAV user is 'web' and his password is 'dav'.
