This plugin runs both
[Midje](https://github.com/marick/Midje) and clojure.test
tests. It has been tested with Leiningen 1.5.2, 1.6.1, and 1.6.2. It
works with Clojure 1.2.0, 1.2.1, and 1.3.0.


Installation
==========

`lein-midje` is available as a plugin:

      $ lein plugin install lein-midje "1.0.8"       # Stable version

[Note: for reasons unknown, you may need to first uninstall
earlier versions.]

Or you can include it in your `project.clj`:

      :dev-dependencies [[lein-midje "1.0.8"]])


Use
==========

To run all the tests, and check all the facts, in both the
`test` and `src` directories, type this:

      $ lein midje 

You can also run individual namespaces by adding them to the
command line:

      $ lein midje life.core life.timecop

You can use a wildcard to specify a subset of namespaces:

       $ lein midje 'midje.ideas.*'

This will run all the tests in that namespace and ones
recursively included within it.

To run `lein-midje` as a watcher process that reloads any
changed test files, use this:

       $ lein midje --lazytest

This requires that the
[lazytest](http://clojars.org/com.intelie/lazytest)
dependency be included in your `project.clj` file, as in:

      [com.intelie/lazytest "1.0.0-SNAPSHOT"]]

Environment Variables
==============

On Unix systems, colorizing of results is turned on by default. It can be
turned off with

      $ export MIDJE_COLORIZE=false

Colorizing is off by default on Windows systems. It can be
turned on with:

      $ export MIDJE_COLORIZE=true

Coloring is most readable with light text against a dark
background. If you use dark text against a light background,
you might prefer this:

      $ export MIDJE_COLORIZE=reverse

It colors the background instead of the letters.

Contributors
==========

* Alex Baranosky
* Andreas Wurzer
* Brian Marick
* dnaumov
