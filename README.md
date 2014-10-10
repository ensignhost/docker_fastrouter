uwsgi fastrouter docker image
=====

This is an image is designed for running [uWSGI](http://uwsgi-docs.readthedocs.org/) in [Fastrouter](http://uwsgi-docs.readthedocs.org/en/latest/Fastrouter.html) mode to with a subscription service. It is based on docker image [ensignavenger/uwsgi-py3](https://registry.hub.docker.com/u/ensignavenger/uwsgi-py3/).

Usage
-----

To run this docker image successfully, you will need the following:

* A uwsgi ini configuration file called subscription.ini in the volume shared as /subscription

This configuration file could do anything, however this image is designed to run a fastrouter, so you may try something like:

```
[uwsgi]
fastrouter = :80
fastrouter = :443
fastrouter-subscription-server = :51823
```

If you plan to expose the subscription port publicly, be sure to add security to prevent anyone from subscribing to your fastrouter!


```
docker run --volume /path/to/code:/code ensignavenger/uwsgi-py3
```
