fs = require 'fs'
{exec} = require 'child_process'

task 'jade', 'converts and puts jade in www', ->
  exec 'jade src/jade -O www/', (err, stdout, stderr) ->
    throw err if err
    console.log 'done jade'

task 'coffee', 'builds coffescript files', ->
  exec 'coffee --compile --output www/js src/coffee', (err, stdout, stderr) ->
    throw err if err
    console.log 'done coffee'

task 'sass', 'sass to css', ->
  exec 'sass --update src/sass:www/stylesheets', (err, stdout, stderr) ->
    throw err if err
    console.log 'did sass'

task 'all', 'Convert jade, coffee and sass', ->
  invoke 'jade'
  invoke 'coffee'
  invoke 'sass'

task 'watch', 'watchr over all', ->
  exec 'watchr watchfile.watchr', (err, stdout, stderr) ->
    throw err if err
    console.log 'watching you'
  invoke 'all'
