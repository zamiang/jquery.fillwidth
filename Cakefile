coffee = require 'coffee-script'
sentry = require 'sentry'
fs = require 'fs'

build = ->
  fs.readFile 'jquery.fillwidth.coffee', (err, data) ->
    fs.writeFile 'jquery.fillwidth.js', coffee.compile data.toString()
    fs.writeFile 'example/src/jquery.fillwidth.js', coffee.compile data.toString()
  console.log 'compiled'

task 'build', 'generate the js for test and in root', build
task 'watch', 'watch for file changes in jquery.fillwidth.coffee and build', ->
  sentry.watch 'jquery.fillwidth.coffee', build
  sentry.watch __dirname + '/test/spec/jquery.fillwidth_spec.coffee', build