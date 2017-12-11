# CROSS-VAR-ISSUE

To reproduce the issue:

```
cd ~/src
git clone https://github.com/arlenyan/cross-var-issue.git
cd cross-var-issue
npm install
```

The output:

```
Arlens-MacBook-Pro:cross-var-issue arlen$ npm install

> cross-var-issue@1.0.0 install /Users/arlen/src/cross-var-issue
> cross-var echo $npm_package_version

/Users/arlen/src/cross-var-issue/node_modules/babel-core/lib/transformation/file/options/option-manager.js:328
        throw e;
        ^

ReferenceError: Unknown plugin "transform-runtime" specified in "/Users/arlen/src/cross-var-issue/node_modules/regenerator-transform/package.json" at 0, attempted to resolve relative to "/Users/arlen/src/cross-var-issue/node_modules/regenerator-transform" (While processing preset: "/Users/arlen/src/cross-var-issue/node_modules/babel-preset-es2015/lib/index.js")
    at /Users/arlen/src/cross-var-issue/node_modules/babel-core/lib/transformation/file/options/option-manager.js:180:17
    at Array.map (native)
    at Function.normalisePlugins (/Users/arlen/src/cross-var-issue/node_modules/babel-core/lib/transformation/file/options/option-manager.js:158:20)
    at OptionManager.mergeOptions (/Users/arlen/src/cross-var-issue/node_modules/babel-core/lib/transformation/file/options/option-manager.js:234:36)
    at OptionManager.init (/Users/arlen/src/cross-var-issue/node_modules/babel-core/lib/transformation/file/options/option-manager.js:368:12)
    at compile (/Users/arlen/src/cross-var-issue/node_modules/babel-register/lib/node.js:103:45)
    at loader (/Users/arlen/src/cross-var-issue/node_modules/babel-register/lib/node.js:144:14)
    at Object.require.extensions.(anonymous function) [as .js] (/Users/arlen/src/cross-var-issue/node_modules/babel-register/lib/node.js:154:7)
    at Module.load (module.js:488:32)
    at tryModuleLoad (module.js:447:12)

npm WARN cross-var-issue@1.0.0 No description
npm ERR! Darwin 17.3.0
npm ERR! argv "/usr/local/Cellar/node/8.9.1/bin/node" "/usr/local/bin/npm" "install"
npm ERR! node v7.9.0
npm ERR! npm  v4.2.0
npm ERR! code ELIFECYCLE
npm ERR! errno 1
npm ERR! cross-var-issue@1.0.0 install: `cross-var echo $npm_package_version`
npm ERR! Exit status 1
npm ERR! 
npm ERR! Failed at the cross-var-issue@1.0.0 install script 'cross-var echo $npm_package_version'.
npm ERR! Make sure you have the latest version of node.js and npm installed.
npm ERR! If you do, this is most likely a problem with the cross-var-issue package,
npm ERR! not with npm itself.
npm ERR! Tell the author that this fails on your system:
npm ERR!     cross-var echo $npm_package_version
npm ERR! You can get information on how to open an issue for this project with:
npm ERR!     npm bugs cross-var-issue
npm ERR! Or if that isn't available, you can get their info via:
npm ERR!     npm owner ls cross-var-issue
npm ERR! There is likely additional logging output above.

npm ERR! Please include the following file with any support request:
npm ERR!     /Users/arlen/.npm/_logs/2017-12-11T23_48_24_682Z-debug.log
```

If you clone the repo to `~/code` instead of `~/src` then it works as intended.