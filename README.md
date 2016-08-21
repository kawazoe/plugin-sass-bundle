# Plugin-Sass Bundling issue

This repository reproduce an issue that happens when the plugin-sass package is bundled through the jspm bundle feature.

# Setup

Use npm to install all npm and jspm dependencies.

```
npm install
```

Then use lite-server to test the application.

```
npm run serve
```

The website will automatically load and display some text with a blue background.

# Reproducing the issue

At this point, all you have to do is bundle the plugin and refresh the page.

```
npm run bundle
```

You will see that the text is now on white background. The debugger console now shows the following error:

```
undefined:1 Uncaught (in promise) Error: (SystemJS) __moduleName is not defined
	ReferenceError: __moduleName is not defined
	    at a.fetchIt$ (http://localhost:3000/build.js:2470:92)
	    at tryCatch (http://localhost:3000/build.js:2008:21)
	    at GeneratorFunctionPrototype.invoke [as _invoke] (http://localhost:3000/build.js:2168:26)
	    at GeneratorFunctionPrototype.prototype.(anonymous function) [as next] (http://localhost:3000/build.js:2032:25)
	    at tryCatch (http://localhost:3000/build.js:2008:21)
	    at invoke (http://localhost:3000/build.js:2060:24)
	    at eval (http://localhost:3000/build.js:2086:15)
	    at Promise.F (http://localhost:3000/build.js:691:38)
	    at callInvokeWithMethodAndArg (http://localhost:3000/build.js:2085:20)
	    at AsyncIterator.enqueue (http://localhost:3000/build.js:2089:133)
	Error loading http://localhost:3000/source.scss!http://localhost:3000/jspm_packages/github/mobilexag/plugin-sass@0.4.6.js as "source.scss!" from http://localhost:3000/source.js
```
