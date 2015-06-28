README
======

Demonstrates packaging an Angular app using setuptools so it can
be combined into Pyramid for easy development.  The essential
instructions for combining a Javascript App and a Python backend
are [provided by Tres Seaver][1].

# Setting Up the Baseline Example

## Contents

 - angseed - seed from [angular/angular-seed](http://github.com:angular/angular-seed)
 - pyrserve - generated using starter scaffold w/ pcreate 

## Creating the Angular & Pyramid Apps

```
mkdir working
git clone git@github.com:angular/angular-seed --depth=1
rm -rf angular-seed/.git
git init
pcreate -s starter pyrserv
cat >README.md "THIS STUFF"
git add .
```            
[1]: https://groups.google.com/forum/#!topic/pylons-discuss/SsBBdi7OQTM








