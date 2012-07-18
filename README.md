Introduction
------------

This is an attempt to easy create a vagrant box that behaves like the Heroku stack that Waterfall normally runs on.

Usages
------
You have two options.  Use the product from a vagrant file or init vagrant yourself.

Init
====
```sh
$ vagrant init waterfall
$ vagrant up
$ vagrant ssh
```

Via Vagrant file
================
Add the following to your `Vagrantfile`.

```ruby
Vagrant::Config.run do |config|
  config.vm.box     = "waterfall"
  config.vm.box_url = "http://<url to waterfall>.box"
end
```


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
$ veewee vbox validate 'waterfall'
$ vagrant basebox export 'waterfall'
```

Now there is a waterfall.box file in your local machine.  You can use it as is or transfer it for other to use.

To use it personally

```sh
$ vagrant box add 'waterfall' 'waterfall.box'
```

References
----------

* vagrant-heroku - https://github.com/ejholmes/vagrant-heroku
* Veewee - https://github.com/jedi4ever/veewee