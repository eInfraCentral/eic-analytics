# Piwik

[![Build Status](https://travis-ci.org/piwik/docker-piwik.svg?branch=master)](https://travis-ci.org/piwik/docker-piwik)

Piwik is the leading open-source analytics platform that gives you more than just powerful analytics:

 - Free open-source software
 - 100% data ownership
 - User privacy protection
 - User-centric insights
 - Customisable and extensible

![logo](https://rawgit.com/piwik/docker-piwik/master/logo.svg)

# How to use this image

The easiest is to use our `docker-compose.yml`.

Make sure you have [docker-compose](http://docs.docker.com/compose/install/) installed. And then:

```bash
git clone https://github.com/eInfraCentral/eic-analytics.git
cd eic-analytics
MYSQL_ROOT_PASSWORD=Your password of choice  docker-compose up -d --build
```

You can now access your instance on the port 8084 of the IP of your machine.

Subsequent launches are done via (the password is ignored):
```bash
docker-compose up -d --build
````

## Access it from Internet

We recommend the usage of TLS, so the easiest is to use a TLS capable reverse proxy.
Here are 2 examples:

 - [haproxy](https://github.com/eInfraCentral/haproxy)
 - [nginx](https://github.com/eInfraCentral/nginx)

You can also modify manually the nginx configuration file and map the TLS port of the host to the container.

## Installation

Once started, you'll arrive at the configuration wizard.
At the `Database Setup` step, please enter the following:

  -  Database Server: `db`
  -  Login: `root`
  -  Password: Your password of choice (from above)
  -  Database Name: piwik (or you can choose)
 
And leave the rest as default.

Then you can continue the installation with the super user.

## Backup

In order to backup, just run the `./pre-backup` script. And copy all the data to a safe place.

## Contribute

Pull requests are very welcome!

We'd love to hear your feedback and suggestions in the issue tracker: [github.com/eInfraCentral/eic-analytics/issues](https://github.com/eInfraCentral/eic-analytics/issues).

## GeoIP

This product includes GeoLite data created by MaxMind, available from
[http://www.maxmind.com](http://www.maxmind.com).
