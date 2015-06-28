# Serving Angular App from Pyramid Backend #

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

## Building Angular App as Python Setuptool Package

Presteps
 - Set up virtualenv and activate it
 - Install npm
 - Add setuptools files as per commit

Build Angular App
```
[Install NPM]
cd angseed
npm install
```

Package and Install as Package
```
[Activate a virtualenv]
python setup.py install
```

## Serving Angular App w/ Pyramid Dev Server

Setup, see routes, and serve pyramid app
```
cd ../pyrserve/
python setup.py develop
proutes development.ini
pserve development.ini --reload
```

Try URLs on localhost
- [The Angular Seed App](http://localhost:6543/)
- [Original Pyramid Root](http://localhost:6543/home)

# The Essential Changes

Quite easy to see these the Change commit, but here they are
anyway.

To package the Angular App as Python Package, added the following:
- [angular-seed/setup.py](angular-seed/setup.py)
- [angular-seed/MANIFEST.in](angular-seed/MANIFEST.in)
- [angular-seed/angseed/__init__.py](angular-seed/angseed/__init__.py)
  Note the includeme() there is just for pyramid use

To add the App as static files to root of pyramid server, based
on [pyramid docs][2]:
- changed [pyrserv/__init__.py](pyrserv/pyrserv/__init__.py)
- added [pyrserv/static.py](pyrserv/pyrserv/static.py)

[1]: https://groups.google.com/forum/#!topic/pylons-discuss/SsBBdi7OQTM
[2]: http://docs.pylonsproject.org/projects/pyramid//en/latest/narr/assets.html#root-relative-custom-static-view-url-dispatch-only











