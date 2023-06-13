# ReproPoly

Reproducing https://github.com/angular/angular-cli/issues/25369

## Changes

Added the following to the `production` builder config (NOTE: Only `aot` and `optimization` appears to be relevant):

```json
{
  "aot": false,
  "buildOptimizer": false,
  "extractLicenses": false,
  "outputHashing": "none",
  "optimization": true,
  "sourceMap": false,
  "vendorChunk": false
}
```

Added the following `.browserslistrc`:

```
> 0.5%
last 2 versions
Firefox ESR
not dead
not IE 9-11 # For IE 9-11 support, remove 'not'.

```

## Steps to reproduce

1. Check out this repo
2. Run `npm install`
3. Run `ng serve --configuration production`
4. Open http://localhost:4200 (F5 in vscode to start Chrome debugger)
5. Notice that the page is empty
6. Open the browser dev tools and notice the error in `polyfills.js`.

```


## Notes

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 16.0.5.
```
