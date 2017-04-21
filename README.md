# npmdoc-esformatter-jsx

#### api documentation for  esformatter-jsx (v8.0.0)  [![npm package](https://img.shields.io/npm/v/npmdoc-esformatter-jsx.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-esformatter-jsx) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-esformatter-jsx.svg)](https://travis-ci.org/npmdoc/node-npmdoc-esformatter-jsx)

#### esformatter plugin: format javascript files that contain React JSX Elements

[![NPM](https://nodei.co/npm/esformatter-jsx.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/esformatter-jsx)

- [https://npmdoc.github.io/node-npmdoc-esformatter-jsx/build/apidoc.html](https://npmdoc.github.io/node-npmdoc-esformatter-jsx/build/apidoc.html)

[![apidoc](https://npmdoc.github.io/node-npmdoc-esformatter-jsx/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-esformatter-jsx/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-esformatter-jsx/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-esformatter-jsx/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "name": "esformatter-jsx",
    "version": "8.0.0",
    "description": "esformatter plugin: format javascript files that contain React JSX Elements",
    "repository": "royriojas/esformatter-jsx",
    "license": "MIT",
    "author": {
        "name": "Roy Riojas",
        "url": "http://royriojas.com"
    },
    "main": "lib/plugin.js",
    "files": [
        "lib/"
    ],
    "engines": {
        "node": ">=0.10.0"
    },
    "prepush": [
        "npm run test"
    ],
    "precommit": [
        "npm run test"
    ],
    "scripts": {
        "autofix": "npm run eslint -- --fix",
        "_lint": "eslint --cache --cache-location='.cache/' -f 'node_modules/eslint-friendly-formatter' ",
        "eslint": "npm run _lint -- 'src/**/*.js' 'specs/**/*.spec.js' ",
        "test": "npm run verify && babel-node node_modules/.bin/mocha-runner 'specs/**/*.spec.js'",
        "cover": "istanbul cover -x 'specs/**/*.spec.js' mocha-runner 'specs/**/*.spec.js' html text-summary",
        "watch": "npm run cover && watch-spawn -p 'specs/**/*.spec.js' npm run cover",
        "verify": "npm run eslint",
        "changelog": "changelogx -f markdown -o ./changelog.md",
        "do-changelog": "npm run changelog && git add ./changelog.md && git commit -m 'DOC: Generate changelog' --no-verify",
        "install-hooks": "prepush install && changelogx install-hook && precommit install",
        "pre-v": "npm run test",
        "post-v": "npm run do-changelog && git push --no-verify && git push --tags --no-verify",
        "bump-major": "npm run pre-v && npm version major -m 'BLD: Release v%s' && npm run post-v",
        "bump-minor": "npm run pre-v && npm version minor -m 'BLD: Release v%s' && npm run post-v",
        "bump-patch": "npm run pre-v && npm version patch -m 'BLD: Release v%s' && npm run post-v",
        "exec-demo": "cd demo && babel-node runner.js",
        "prepublish": "npm run build",
        "build": "babel src/ -d lib/"
    },
    "keywords": [
        "esformatter-plugin",
        "esformatter",
        "jsx",
        "react jsx",
        "AST",
        "codestyle",
        "react jsx"
    ],
    "peerDependencies": {},
    "dependencies": {
        "babylon": "6.14.1",
        "esformatter-ignore": "^0.1.3",
        "extend": "3.0.0",
        "js-beautify": "1.6.12",
        "js-beautify-ejsx": "1.6.12"
    },
    "devDependencies": {
        "babel-cli": "6.18.0",
        "babel-eslint": "7.1.1",
        "babel-plugin-add-module-exports": "0.2.1",
        "babel-plugin-transform-decorators-legacy": "1.3.4",
        "babel-polyfill": "6.16.0",
        "babel-preset-es2015": "6.18.0",
        "babel-preset-react": "6.16.0",
        "babel-preset-stage-0": "6.16.0",
        "chalk": "^1.1.3",
        "changelogx": "^1.0.18",
        "colors": "^1.1.2",
        "diff": "^2.2.3",
        "esbeautifier": "^3.2.0",
        "esformatter": "^0.9.5",
        "esformatter-quotes": "^1.1.0",
        "eslint": "3.11.0",
        "eslint-config-airbnb": "13.0.0",
        "eslint-friendly-formatter": "2.0.6",
        "eslint-plugin-import": "2.2.0",
        "eslint-plugin-jsx-a11y": "2.2.3",
        "eslint-plugin-mocha": "4.7.0",
        "eslint-plugin-react": "6.7.1",
        "istanbul": "^0.3.17",
        "mkdirp": "^0.5.1",
        "mocha-runner": "^1.1.2",
        "precommit": "^1.2.0",
        "prepush": "^3.1.8",
        "proxyquire": "^1.6.0",
        "read-json-sync": "^1.1.0",
        "watch-spawn": "^1.0.3"
    },
    "changelogx": {
        "ignoreRegExp": [
            "BLD: Release",
            "DOC: Generate Changelog",
            "Generated Changelog"
        ],
        "issueIDRegExp": "#(\\d+)",
        "commitURL": "https://github.com/royriojas/esformatter-jsx/commit/{0}",
        "authorURL": "https://github.com/{0}",
        "issueIDURL": "https://github.com/royriojas/esformatter-jsx/issues/{0}",
        "projectName": "esformatter-jsx"
    },
    "bin": {}
}
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
