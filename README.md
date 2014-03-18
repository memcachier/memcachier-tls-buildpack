# MemCachier TLS Buildpack

A [buildpack] for connecting to MemCachier over TLS from non-TLS supporting
clients. The builpack installs and sets up [stunnel] on localhost listening
on port 11211. It configures stunnel to connect to the MemCachier servers
specified in your environment variable and to verify certificates as signed by
the [MemCachier Root CA](https://www.memcachier.com/MemCachierRootCA.pem).

## Usage

You must use this buildpack in conjunction with another buildpack that actually
runs your app. To do so, first configure your app to use the
[multi-buildpack](https://github.com/ddollar/heroku-buildpack-multi):

    $ heroku config:add BUILDPACK_URL=https://github.com/ddollar/heroku-buildpack-multi.git

Next, add a `.buildpacks` file to your app repository. The file should contain
the Git URL of each buildpack you'd like to use, including this one. For
example, to run a Python app with TLS support for MemCachier, your
`.buildpacks` file should look like this:

    $ cat .buildpacks
    https://github.com/heroku/heroku-buildpack-python.git
    https://github.com/memcachier/memcachier-tls-buildpack.git

Finally, configure your app to connect to `localhost:11211` instead of using
the `MEMCACHIER_SERVERS` environment variable and deploy!

## Licensing

This library is under the AGPLv3

## Get involved!

We are happy to receive bug reports, fixes, documentation enhancements,
and other improvements.

Please report bugs via the
[github issue tracker](http://github.com/memcachier/memcachier-tls-buildpack/issues).

Master [git repository](http://github.com/memcachier/memcachier-tls-buildpack):

* `git clone git://github.com/memcachier/memcachier-tls-buildpack.git`

## Authors

This library is written and  maintained by MemCachier,
<info@memcachier.com>.

[buildpack]: https://devcenter.heroku.com/articles/buildpacks
[stunnel]: https://www.stunnel.org/index.html
