# JS Module
Boilerplate for starting an es2015 js module using babel to transpile and
webpack to build.<br>
*note: does not make assumption about node or browser environment

##Prerequisite
Have [starter-deck-cli](https://github.com/esayemm/starter-deck-cli) installed
globally.

##Installation
```sh
sdcli save jsmodule https://github.com/esayemm/starter-deck_js-module
```
<hr>

##Development

####Regular development
Interact with module in example/index.js

```
npm start
```

####Publish a release
Use [npm version](https://docs.npmjs.com/cli/version) and follow [semver](http://semver.org/) rules.<br>

```
npm version [ major | minor | patch ]
```

1. bumps package version
2. creates git tag
3. push tag
4. builds
5. npm publish

####Existing app without publishing
To test integration into existing applications without npm publishing module use [npm link](https://docs.npmjs.com/cli/link). Be sure to run the following to transpile src first.

```
npm run prerelease
```

1. Inside module project dir run `npm link`
2. Go into existing app dir and run `npm link <name_of_package>`