Introduction
------------

This is an attempt to easy create a vagrant box that behaves like the Heroku stack that Waterfall normally runs on.

Developer Notes
---------------

``` sh
$ git clone git://github.com/WaterfallFMS/waterfall-heroku-vagrant.git
$ cd waterfall-heroku-vagrant
$ bundle install
$ bundle exec veewee vbox define waterfall ubuntu-12.04-server-i386
```

Edit the `definitions/waterfall` files.

```sh
$ veewee vbox build 'waterfall'
```

References
----------

* vagrant-heroku - https://github.com/ejholmes/vagrant-heroku
* Veewee - https://github.com/jedi4ever/veewee