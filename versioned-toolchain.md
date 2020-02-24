### Introduction

The standard template setup instructions feature a toolchain that is installed globally with the following command:
```
npm install --global purescript spago parcel
```

Using global tools is a fine strategy when starting-out with PureScript, or if you plan to always keep-up with the latest and greatest compiler version and package sets, but you may later find yourself in situations where you want to use a different compiler version on a per-project basis.

Our templates are easily configurable to use a local versioned toolchain.

### Instructions

Start from a cloned template:
```
git clone --depth 1 https://github.com/purescript-templates/halogen.git myApp
cd myApp
```

The required tools and their versions for this template are listed in the `devDependencies` section of `package.json`:
``` json
  "devDependencies": {
    "parcel": "^1.12.4",
    "purescript": "^0.13.6",
    "spago": "^0.14.0"
  }
```

Install dependencies locally:
```
npm install
```

This installs all the necessary tools to `<path-to>/myApp/node_modules/.bin/`.

Prefix tooling commands with `npx` to select the local version.
```
npx spago build
```

Add new tools or upgrade tool versions in your project with the `--save-dev` flag:
```
npm install --save-dev purescript spago parcel
```

Feel free to use your discretion in deciding which tools are worth tracking locally.
A major version bump of `parcel` is unlikely to break your project.
But you may have dependencies that rely on a particular `purescript` compiler version and `spago` package set.