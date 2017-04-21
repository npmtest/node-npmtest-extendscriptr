# npmtest-extendscriptr

#### basic test coverage for  [extendscriptr (v1.1.1)](https://github.com/ExtendScript/extendscriptr#readme)  [![npm package](https://img.shields.io/npm/v/npmtest-extendscriptr.svg?style=flat-square)](https://www.npmjs.org/package/npmtest-extendscriptr) [![travis-ci.org build-status](https://api.travis-ci.org/npmtest/node-npmtest-extendscriptr.svg)](https://travis-ci.org/npmtest/node-npmtest-extendscriptr)

#### A node build configuration to develop extendScripts with es2015 javascript code

[![NPM](https://nodei.co/npm/extendscriptr.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/extendscriptr)

| git-branch : | [alpha](https://github.com/npmtest/node-npmtest-extendscriptr/tree/alpha)|
|--:|:--|
| coverage : | [![istanbul-coverage](https://npmtest.github.io/node-npmtest-extendscriptr/build/coverage.badge.svg)](https://npmtest.github.io/node-npmtest-extendscriptr/build/coverage.html/index.html)|
| test-report : | [![test-report](https://npmtest.github.io/node-npmtest-extendscriptr/build/test-report.badge.svg)](https://npmtest.github.io/node-npmtest-extendscriptr/build/test-report.html)|
| build-artifacts : | [![build-artifacts](https://npmtest.github.io/node-npmtest-extendscriptr/glyphicons_144_folder_open.png)](https://github.com/npmtest/node-npmtest-extendscriptr/tree/gh-pages/build)|

- [https://npmtest.github.io/node-npmtest-extendscriptr/build/coverage.html/index.html](https://npmtest.github.io/node-npmtest-extendscriptr/build/coverage.html/index.html)

[![istanbul-coverage](https://npmtest.github.io/node-npmtest-extendscriptr/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fcoverage.lib.html.png)](https://npmtest.github.io/node-npmtest-extendscriptr/build/coverage.html/index.html)

- [https://npmtest.github.io/node-npmtest-extendscriptr/build/test-report.html](https://npmtest.github.io/node-npmtest-extendscriptr/build/test-report.html)

[![test-report](https://npmtest.github.io/node-npmtest-extendscriptr/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Ftest-report.html.png)](https://npmtest.github.io/node-npmtest-extendscriptr/build/test-report.html)

- [https://npmdoc.github.io/node-npmdoc-extendscriptr/build/apidoc.html](https://npmdoc.github.io/node-npmdoc-extendscriptr/build/apidoc.html)

[![apidoc](https://npmdoc.github.io/node-npmdoc-extendscriptr/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-extendscriptr/build/apidoc.html)

![npmPackageListing](https://npmtest.github.io/node-npmtest-extendscriptr/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmtest.github.io/node-npmtest-extendscriptr/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "bin": {
        "extendscriptr": "./index.js"
    },
    "version": "1.1.1",
    "name": "extendscriptr",
    "description": "A node build configuration to develop extendScripts with es2015 javascript code",
    "scripts": {
        "commit": "git-cz",
        "quatsch": "do",
        "clean:temp": "rm -rf ./.tmp ; mkdir ./.tmp",
        "clean:dist": "rm -rf ./test/dist ; mkdir ./test/dist",
        "compile:test:illustrator": "node ./index.js -s test/src/illustrator.js -o test/dist/illustrator.js -t 'illustrator'",
        "compile:test:indesign": "node ./index.js -s test/src/indesign.js -o test/dist/indesign.js -t 'indesign'",
        "compile:test:indesign-basil": "./node_modules/.bin/exsbundlr -i test/src/indesign-basil.js -o test/dist/indesign-basil.bundle.js & node ./index.js -s test/dist/indesign-basil.bundle.js -o test/dist/indesign-basil.js",
        "compile:test:aftereffects": "node ./index.js -s test/src/aftereffects.js -o test/dist/aftereffects.js -t 'aftereffects'",
        "compile:test:photoshop": "node ./index.js -s test/src/photoshop.js -o test/dist/photoshop.js -t 'photoshop'",
        "compile:test:all": "npm run compile:test:illustrator & npm run compile:test:indesign & npm run compile:test:indesign-basil & npm run compile:test:aftereffects & npm run compile:test:photoshop",
        "test": "npm run clean:dist ; npm run compile:test:all ; npm run clean:temp",
        "semantic-release": "semantic-release pre && npm publish && semantic-release post"
    },
    "repository": {
        "type": "git",
        "url": "https://github.com/ExtendScript/extendscriptr.git"
    },
    "keywords": [
        "automation",
        "build",
        "process",
        "extendScript",
        "indesign",
        "illustrator",
        "photoshop",
        "adobe",
        "es2105",
        "es6",
        "compile"
    ],
    "author": "vogelino",
    "license": "WTFPL",
    "bugs": {
        "url": "https://github.com/ExtendScript/extendscriptr/issues"
    },
    "homepage": "https://github.com/ExtendScript/extendscriptr#readme",
    "dependencies": {
        "babel": "^6.5.2",
        "babel-plugin-transform-es3-member-expression-literals": "^6.5.0",
        "babel-plugin-transform-es3-property-literals": "^6.5.0",
        "babel-plugin-transform-es5-property-mutators": "^6.6.5",
        "babel-preset-es2015": "^6.6.0",
        "babelify": "^7.3.0",
        "browserify": "^13.0.0",
        "commander": "^2.9.0",
        "extendscript.prototypes": "0.0.8",
        "prependify": "^1.2.0"
    },
    "devDependencies": {
        "babel-eslint": "^6.0.4",
        "commitizen": "^2.8.1",
        "cz-conventional-changelog": "^1.1.6",
        "extendscript-bundlr": "^0.3.1",
        "semantic-release": "^4.3.5"
    },
    "config": {
        "commitizen": {
            "path": "./node_modules/cz-conventional-changelog"
        }
    },
    "engineStrict": true,
    "engines": {
        "npm": ">=3.0.0"
    }
}
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
