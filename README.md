# MemCachier TLS Buildpack

A [buildpack] for connecting to MemCachier over TLS from non-TLS supporting
clients. The buildpack installs and sets up [stunnel] on localhost listening
on port 11211. It configures stunnel to connect to the MemCachier servers
specified in your environment variable and to verify certificates as signed by
the [MemCachier Root CA](https://www.memcachier.com/MemCachierRootCA.pem).

## Usage

Heroku now has native support for [multiple buildpacks], so simply run:

    $ heroku buildpacks:add -i 1 https://github.com/memcachier/memcachier-tls-buildpack.git

Finally, configure your app to connect to `localhost:11211` instead of using
the `MEMCACHIER_SERVERS` environment variable and deploy!

## Licensing

This library is under the AGPLv3

## Get involved!

We are happy to receive bug reports, fixes, documentation enhancements,
and other improvements.

Please report bugs via the
[github issue tracker](https://github.com/memcachier/memcachier-tls-buildpack/issues).

Master [git repository](https://github.com/memcachier/memcachier-tls-buildpack):

* `git clone git://github.com/memcachier/memcachier-tls-buildpack.git`

## Authors

This library is written and  maintained by MemCachier,
<info@memcachier.com>.

[buildpack]: https://devcenter.heroku.com/articles/buildpacks
[stunnel]: https://www.stunnel.org/index.html
[multiple buildpacks]: https://devcenter.heroku.com/articles/using-multiple-buildpacks-for-an-app
