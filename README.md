# api documentation for  [sloc (v0.2.0)](https://github.com/flosse/sloc#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-sloc.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-sloc) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-sloc.svg)](https://travis-ci.org/npmdoc/node-npmdoc-sloc)
#### sloc is a simple tool to count SLOC (source lines of code)

[![NPM](https://nodei.co/npm/sloc.png?downloads=true)](https://www.npmjs.com/package/sloc)

[![apidoc](https://npmdoc.github.io/node-npmdoc-sloc/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-sloc_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-sloc/build/apidoc.html)

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
            "name": "flosse",
            "email": "mail@markus-kohlhase.de"
        }
    ],
    "name": "sloc",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
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



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module sloc](#apidoc.module.sloc)
1.  object <span class="apidocSignatureSpan">sloc.</span>extensions
1.  object <span class="apidocSignatureSpan">sloc.</span>formatters
1.  object <span class="apidocSignatureSpan">sloc.</span>helpers
1.  object <span class="apidocSignatureSpan">sloc.</span>keys

#### [module sloc.formatters](#apidoc.module.sloc.formatters)
1.  [function <span class="apidocSignatureSpan">sloc.formatters.</span>cli-table (data, options, fmtOpts)](#apidoc.element.sloc.formatters.cli-table)
1.  [function <span class="apidocSignatureSpan">sloc.formatters.</span>csv (data, options)](#apidoc.element.sloc.formatters.csv)
1.  [function <span class="apidocSignatureSpan">sloc.formatters.</span>json (res, options, fmtOpts)](#apidoc.element.sloc.formatters.json)
1.  [function <span class="apidocSignatureSpan">sloc.formatters.</span>simple (data, options, fmtOpts)](#apidoc.element.sloc.formatters.simple)

#### [module sloc.helpers](#apidoc.module.sloc.helpers)
1.  [function <span class="apidocSignatureSpan">sloc.helpers.</span>alignRight (string, width)](#apidoc.element.sloc.helpers.alignRight)
1.  [function <span class="apidocSignatureSpan">sloc.helpers.</span>summarize (fileStats)](#apidoc.element.sloc.helpers.summarize)



# <a name="apidoc.module.sloc"></a>[module sloc](#apidoc.module.sloc)



# <a name="apidoc.module.sloc.formatters"></a>[module sloc.formatters](#apidoc.module.sloc.formatters)

#### <a name="apidoc.element.sloc.formatters.cli-table"></a>[function <span class="apidocSignatureSpan">sloc.formatters.</span>cli-table (data, options, fmtOpts)](#apidoc.element.sloc.formatters.cli-table)
- description and source-code
```javascript
cli-table = function (data, options, fmtOpts) {
  var d, ext, f, head, heads, i, k, keys, len, ref, ref1, s, statToArray, table;
  keys = options.keys || sloc.keys;
  heads = options.details ? ['Path'].concat(slice.call(keys)) : ['Extension'].concat(slice.call(keys));
  head = indexOf.call(fmtOpts, 'no-head') >= 0 ? [] : (function() {
    var i, len, results;
    results = [];
    for (i = 0, len = heads.length; i < len; i++) {
      k = heads[i];
      results.push(i18n.en[k]);
    }
    return results;
  })();
  table = new Table({
    head: head
  });
  statToArray = function(d) {
    var i, len, results;
    results = [];
    for (i = 0, len = keys.length; i < len; i++) {
      k = keys[i];
      results.push(d[k]);
    }
    return results;
  };
  if (options.details) {
    ref = data.files;
    for (i = 0, len = ref.length; i < len; i++) {
      f = ref[i];
      table.push([f.path].concat(slice.call(statToArray(f.stats))));
    }
  } else if ((s = data.summary) != null) {
    table.push(['- Total -'].concat(slice.call(statToArray(s))));
    ref1 = data.byExt;
    for (ext in ref1) {
      d = ref1[ext];
      if ((s = d.summary) != null) {
        table.push([ext].concat(slice.call(statToArray(s))));
      }
    }
  }
  return table.toString();
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.sloc.formatters.csv"></a>[function <span class="apidocSignatureSpan">sloc.formatters.</span>csv (data, options)](#apidoc.element.sloc.formatters.csv)
- description and source-code
```javascript
csv = function (data, options) {
  var f, i, k, len, lineize, lines, ref, s;
  if (options == null) {
    options = {};
  }
  if (data == null) {
    return console.error("Error: missing data");
  }
  lines = i18n.en.Path + "," + (((function() {
    var i, len, ref, results;
    ref = sloc.keys;
    results = [];
    for (i = 0, len = ref.length; i < len; i++) {
      k = ref[i];
      results.push(i18n.en[k]);
    }
    return results;
  })()).join(',')) + "\n";
  lineize = function(t) {
    return ((function() {
      var i, len, ref, results;
      ref = sloc.keys;
      results = [];
      for (i = 0, len = ref.length; i < len; i++) {
        k = ref[i];
        results.push(t[k]);
      }
      return results;
    })()).join(',');
  };
  if (options.details) {
    ref = data.files;
    for (i = 0, len = ref.length; i < len; i++) {
      f = ref[i];
      if (f.stats != null) {
        lines += f.path + "," + (lineize(f.stats)) + "\n";
      }
    }
  } else if ((s = data.summary) != null) {
    lines += i18n.en.Total + ',' + lineize(s);
  }
  if (lines[lines.length - 1] === '\n') {
    lines = lines.slice(0, -1);
  }
  return lines;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.sloc.formatters.json"></a>[function <span class="apidocSignatureSpan">sloc.formatters.</span>json (res, options, fmtOpts)](#apidoc.element.sloc.formatters.json)
- description and source-code
```javascript
json = function (res, options, fmtOpts) {
  return JSON.stringify(res, null, (indexOf.call(fmtOpts, 'no-indent') >= 0 ? 0 : 2));
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.sloc.formatters.simple"></a>[function <span class="apidocSignatureSpan">sloc.formatters.</span>simple (data, options, fmtOpts)](#apidoc.element.sloc.formatters.simple)
- description and source-code
```javascript
simple = function (data, options, fmtOpts) {
  var badFiles, bl, d, f, fileCount, result;
  if (options == null) {
    options = {};
  }
  if (options.keys == null) {
    options.keys = sloc.keys;
  }
  result = "\n---------- " + i18n.en.Result + " ------------\n\n";
  result += stat({
    stats: data.summary
  }, options);
  badFiles = data.files.filter(function(x) {
    return x.badFile;
  });
  fileCount = data.files.length - badFiles.length;
  result += "\n\n" + i18n.en.NumberOfFilesRead + " :  " + fileCount;
  if (bl = badFiles.length > 0) {
    result += "\n" + (align(i18n.en.BrokenFiles, col)) + " :  " + (String(badFiles.length).red);
  }
  if (options.details && data.files.length > 1) {
    result += "\n\n---------- " + i18n.en.Details + " -----------\n";
    d = (function() {
      var j, len, ref, results;
      ref = data.files;
      results = [];
      for (j = 0, len = ref.length; j < len; j++) {
        f = ref[j];
        results.push("\n\n--- " + f.path + "\n\n" + (stat(f, options)));
      }
      return results;
    })();
    result += d.join('');
  }
  return result += "\n\n------------------------------\n";
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.sloc.helpers"></a>[module sloc.helpers](#apidoc.module.sloc.helpers)

#### <a name="apidoc.element.sloc.helpers.alignRight"></a>[function <span class="apidocSignatureSpan">sloc.helpers.</span>alignRight (string, width)](#apidoc.element.sloc.helpers.alignRight)
- description and source-code
```javascript
alignRight = function (string, width) {
  if (string == null) {
    string = '';
  }
  if (width == null) {
    width = 0;
  }
  if (!(typeof string === 'string' && typeof width === 'number' && width >= 0)) {
    return '';
  }
  if (string.length >= width) {
    return string.slice(-width);
  } else {
    return Array(width - string.length + 1).join(' ') + string;
  }
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.sloc.helpers.summarize"></a>[function <span class="apidocSignatureSpan">sloc.helpers.</span>summarize (fileStats)](#apidoc.element.sloc.helpers.summarize)
- description and source-code
```javascript
summarize = function (fileStats) {
  if (!(Array.isArray(fileStats) && fileStats.length > 0)) {
    return {};
  }
  return fileStats.reduce(function(a, b) {
    var i, k, len, o, ref, v, x;
    o = {};
    ref = [a, b];
    for (i = 0, len = ref.length; i < len; i++) {
      x = ref[i];
      if (x != null) {
        for (k in x) {
          v = x[k];
          if (!(typeof v === "number")) {
            continue;
          }
          if (o[k] == null) {
            o[k] = 0;
          }
          o[k] += v;
        }
      }
    }
    return o;
  });
}
```
- example usage
```shell
n/a
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
