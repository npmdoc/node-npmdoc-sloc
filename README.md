# npmdoc-sloc

#### api documentation for  [sloc (v0.2.0)](https://github.com/flosse/sloc#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-sloc.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-sloc) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-sloc.svg)](https://travis-ci.org/npmdoc/node-npmdoc-sloc)

#### sloc is a simple tool to count SLOC (source lines of code)

[![NPM](https://nodei.co/npm/sloc.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/sloc)

- [https://npmdoc.github.io/node-npmdoc-sloc/build/apidoc.html](https://npmdoc.github.io/node-npmdoc-sloc/build/apidoc.html)

[![apidoc](https://npmdoc.github.io/node-npmdoc-sloc/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-sloc/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-sloc/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-sloc/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Markus Kohlhase"
    },
    "bin": {
        "sloc": "bin/sloc"
    },
    "bugs": {
        "url": "http://github.com/flosse/sloc/issues"
    },
    "contributors": [
        {
            "name": "Markus Kohlhase"
        },
        {
            "name": "feugy"
        },
        {
            "name": "Sören Gade"
        },
        {
            "name": "as3boyan"
        },
        {
            "name": "Mark Hahn"
        },
        {
            "name": "Hubert Sablonniere"
        },
        {
            "name": "programmerby"
        },
        {
            "name": "daclayton"
        },
        {
            "name": "Steven Vachon"
        },
        {
            "name": "yoshi6jp"
        },
        {
            "name": "Casper Hollingberry"
        },
        {
            "name": "Tobie Warburton"
        }
    ],
    "dependencies": {
        "async": "~2.1.4",
        "cli-table": "^0.3.1",
        "commander": "~2.9.0",
        "readdirp": "^2.1.0"
    },
    "description": "sloc is a simple tool to count SLOC (source lines of code)",
    "devDependencies": {
        "chai": "~3.5.0",
        "coffee-script": "~1.12.3",
        "coffeelint": "^1.16.0",
        "coveralls": "^2.11.15",
        "istanbul": "^0.4.5",
        "mocha": "~3.2.0"
    },
    "directories": {},
    "dist": {
        "shasum": "b42d3da1a442a489f454c32c628e8ebf0007875c",
        "tarball": "https://registry.npmjs.org/sloc/-/sloc-0.2.0.tgz"
    },
    "engine": "node",
    "files": [
        "bin",
        "lib"
    ],
    "gitHead": "3fcf6877cc5ae04dd628372ca09a836fab28c2e9",
    "homepage": "https://github.com/flosse/sloc#readme",
    "license": "MIT",
    "main": "lib/sloc",
    "maintainers": [
        {
            "name": "flosse"
        }
    ],
    "name": "sloc",
    "optionalDependencies": {},
    "repository": {
        "type": "git",
        "url": "git://github.com/flosse/sloc.git"
    },
    "scripts": {
        "lint": "coffeelint src/",
        "prepublish": "coffee -o lib/ -c src/",
        "test": "npm run lint && mocha --reporter spec --compilers coffee:coffee-script/register --recursive spec/*.spec.coffee",
        "watch": "coffee -o lib -cw src/"
    },
    "version": "0.2.0"
}
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
