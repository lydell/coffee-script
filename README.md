# Upgrade `@param`s to CoffeeScript 1.9.0+

CoffeeScript versions prior to 1.9.0 accidentally allowed this:

```coffee
class Person
  constructor: (@name) ->
    console.log(name)
```

In CoffeeScript 1.9.0+ the above will throw a `ReferenceError` since you’re
trying to log an undefined variable. The correct way to write it is:

```coffee
class Person
  constructor: (@name) ->
    console.log(@name)
```

In other words, you used to be able to access `@param`s without the `@`, but
cannot anymore.

This mod of the CoffeeScript compiler `console.error`s each occurance where you
are missing a `@`.

To install it:

```sh
npm install lydell/coffee-script#1.8-at-params-warn
```

To check a file for missing `@`s, run for example:

```sh
./node_modules/.bin/coffee -p file-to-check.coffee >/dev/null
```

Fix all warnings and then you should be good to go to upgrade to CoffeeScript
1.9.0+!

Orignal CoffeeScript README:

            {
         }   }   {
        {   {  }  }
         }   }{  {
        {  }{  }  }                    _____       __  __
       { }{ }{  { }                   / ____|     / _|/ _|
     .- { { }  { }} -.               | |     ___ | |_| |_ ___  ___
    (  { } { } { } }  )              | |    / _ \|  _|  _/ _ \/ _ \
    |`-..________ ..-'|              | |___| (_) | | | ||  __/  __/
    |                 |               \_____\___/|_| |_| \___|\___|
    |                 ;--.
    |                (__  \            _____           _       _
    |                 | )  )          / ____|         (_)     | |
    |                 |/  /          | (___   ___ _ __ _ _ __ | |_
    |                 (  /            \___ \ / __| '__| | '_ \| __|
    |                 |/              ____) | (__| |  | | |_) | |_
    |                 |              |_____/ \___|_|  |_| .__/ \__|
     `-.._________..-'                                  | |
                                                        |_|

CoffeeScript is a little language that compiles into JavaScript.

## Installation

If you have the node package manager, npm, installed:

```shell
npm install -g coffee-script
```

Leave off the `-g` if you don't wish to install globally. If you don't wish to use npm:

```shell
git clone https://github.com/jashkenas/coffeescript.git
sudo coffeescript/bin/cake install
```

## Getting Started

Execute a script:

```shell
coffee /path/to/script.coffee
```

Compile a script:

```shell
coffee -c /path/to/script.coffee
```

For documentation, usage, and examples, see: http://coffeescript.org/

To suggest a feature or report a bug: http://github.com/jashkenas/coffeescript/issues

If you'd like to chat, drop by #coffeescript on Freenode IRC.

The source repository: https://github.com/jashkenas/coffeescript.git

Changelog: http://coffeescript.org/#changelog

Our lovely and talented contributors are listed here: http://github.com/jashkenas/coffeescript/contributors
