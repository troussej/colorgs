# Colorgs - A Log Colorizer
===

An attempt at a more detailed colorizer than [Kelly Goetsch's classic tool]( http://atglogcolorizer.sourceforge.net ), extended for other languages and format than ATG

The goal it to highlight more than just log level : patterns like stacktraces, pipeline logs, and more

## Features
  - color each type of log level
  - highlight pipeline logs : keywords, chain names, return values
  - highlight stacktraces :  exceptions, class name & line number
  - highlight component names, some key atg logs (Nucleus Starting), key/value pairs (ex: order=o10000)
  - filter out elements of the logs, if one has no control over the output pattern

## Examples

With [solarized](http://ethanschoonover.com/solarized) terminal colors

![Screenshot 1](img/example.png "colorgs in action!")



## Install

`npm i -g colorgs`

## Usage:

The colorgs command reads from the standard output and writes a colorized log 

`tail -f file.log | colorgs`

In order to use it with less, you must pass the -R flag to less, so that less applies the color codes.

`cat file.log | colorgs | less -R`

note : taking a file as stdin is on the wishlist

## Disclamer - Known Limitations

### Functionnal 

colorgs is based on a parser that must recognize the whole line pattern. Small deviations in the pattern can lead the tool to fail to recognize a line. For now the recognized patterns are limited to ones I've encountered in the projects I worked on. With time the library of patterns will grow. I also intend on making the tool customizable (pattern & color schemes) so that anyone can easily adapt it to their needs.

### Performances

colorgs runs on nodejs, it's obviously slower than the original C++ tool. For now it looks fine.


## Changelog

### Todo

 - customizable patterns
 - customizable color scheme

## [0.0.6]
Added:
 -  sql block colorizing

## [0.0.2]
Fixed:
 - install

### [0.0.1] Initial Version
Added:

 - Level detection
 - Some basic patterns

 #TODO

  - read file from stdin
  - change to node-ts