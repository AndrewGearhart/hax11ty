# HAXcms Eleventy Starter

## Development

### Install Dependencies

```
yarn install
```

### Start Development Server

```
yarn start
```

Visit http://localhost:8000/

## Notes for Unbundled Builds

Retrieve the repo for unbundled builds and put it into the root directory of hax11ty

```
├── hax11ty
│   ├── ...
│   ├── unbundled-webcomponents
```

* Edit `unbundled-webcomponents/app/package.json > {} dependencies` to include your dependencies
* Edit `unbundled-webcomponents/app/src/app.js` to include the following:  
```
import "@lrnwebcomponents/haxcms-elements/lib/core/haxcms-site-builder.js";
import "@lrnwebcomponents/learn-two-theme/learn-two-theme.js";
import "@npm-org/componentname/componentname.js";
```
* Run `yarn install` from the hax11ty/unbundled-webcomponents/ directory
* Run `yarn run build` from the hax11ty/unbundled-webcomponents/ directory
* Change from Pro to HaxCMS Mode:  
In the `_data/settings.js` change the `mode: "pro"` -> `mode: "haxcms"`

## Retrieve HAXCMS Pages

* Copy pages from `_sites/<sitename>/pages`
* Update your pages to have "gray matter" headings
* Update your pages to be named *.md rather than *.html

## Build the hax11ty node_modules

At /hax11ty `yarn install`

## If your components have any extraDependencies 

Items such as .css files, .map, .js in unusual locations, include them in unbundled-webcomponents/app/polymer.json 

## Perform Custom Build w/ Other Web Components

```
rm -rf build               
rm wc-registry.json 
rm build.js
cp -r unbundled-webcomponents/app/dist/assets .
cp -r unbundled-webcomponents/app/dist/build . 
cp -r unbundled-webcomponents/app/dist/build.js .
cp -r unbundled-webcomponents/app/dist/wc-registry.json .
```

## If Staging in a subdirectory, fix basepaths

* update href/src in _site/index.html
* update href/src in each of the posts
