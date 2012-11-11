# example.js

``` javascript
function getTemplate(templateName, callback) {
	require(["../require.context/templates/"+templateName], function(tmpl) {
		callback(tmpl());
	});
}
getTemplate("a", function(a) {
	console.log(a);
});
getTemplate("b", function(b) {
	console.log(b);
});
```

# js/output.js

``` javascript
/******/(function(document, undefined) {
/******/	return function(modules) {
/******/		var installedModules = {}, installedChunks = {0:1};
/******/		function require(moduleId) {
/******/			if(typeof moduleId !== "number") throw new Error("Cannot find module '"+moduleId+"'");
/******/			if(installedModules[moduleId])
/******/				return installedModules[moduleId].exports;
/******/			var module = installedModules[moduleId] = {
/******/				exports: {},
/******/				id: moduleId,
/******/				loaded: false
/******/			};
/******/			modules[moduleId](module, module.exports, require);
/******/			module.loaded = true;
/******/			return module.exports;
/******/		}
/******/		require.e = function(chunkId, callback) {
/******/			if(installedChunks[chunkId] === 1) return callback(require);
/******/			if(installedChunks[chunkId] !== undefined)
/******/				installedChunks[chunkId].push(callback);
/******/			else {
/******/				installedChunks[chunkId] = [callback];
/******/				var head = document.getElementsByTagName('head')[0];
/******/				var script = document.createElement('script');
/******/				script.type = 'text/javascript';
/******/				script.charset = 'utf-8';
/******/				script.src = modules.c+chunkId+modules.a;
/******/				head.appendChild(script);
/******/			}
/******/		};
/******/		require.modules = modules;
/******/		require.cache = installedModules;
/******/		window[modules.b] = function(chunkId, moreModules) {
/******/			for(var moduleId in moreModules)
/******/				modules[moduleId] = moreModules[moduleId];
/******/			var callbacks = installedChunks[chunkId];
/******/			installedChunks[chunkId] = 1;
/******/			for(var i = 0; i < callbacks.length; i++)
/******/				callbacks[i](require);
/******/		};
/******/		return require(0);
/******/	}
/******/})(document)
/******/({a:".output.js",b:"webpackJsonp",c:"",
/******/0: function(module, exports, require) {

/**! .\example.js !**/

/******/ /* WEBPACK FREE VAR INJECTION */ (function(require,console) {
function getTemplate(templateName, callback) {
	require(1, function() { return [require(/*! ../require.context/templates */4)("./"+templateName)]}, function(tmpl) {
		callback(tmpl());
	});
}
getTemplate("a", function(a) {
	console.log(a);
});
getTemplate("b", function(b) {
	console.log(b);
});
/******/ /* WEBPACK FREE VAR INJECTION */ }(require(/*! __webpack_amd_require */2),require(/*! __webpack_console */1)))

/******/},
/******/
/******/1: function(module, exports, require) {

/**! (webpack)\buildin\__webpack_console.js !**/

var console = (function() { return this["console"] || (this["window"] && this["window"].console) || {} }());
module.exports = console;
for(var name in {log:1, info:1, error:1, warn:1, dir:1, trace:1, assert:1})
	if(!console[name])
		console[name] = function() {};
var times = {};
if(!console.time)
console.time = function(label) {
	times[label] = Date.now();
};
if(!console.timeEnd)
console.timeEnd = function() {
	var duration = Date.now() - times[label];
	console.log('%s: %dms', label, duration);
};

/******/},
/******/
/******/2: function(module, exports, require) {

/**! (webpack)\buildin\__webpack_amd_require.js !**/

var req = require.valueOf();
function amdRequire(chunk, requiresFn, fn) {
	if(!requiresFn) {
		// commonjs
		return req(chunk);
	}
	req.e(chunk, function() {
		var modules = requiresFn();
		if(fn)
			return fn.apply(null, modules);
	});
}
for(var name in req)
	amdRequire[name] = req[name];
amdRequire.amd = require(/*! ./__webpack_options_amd.loader.js!./__webpack_options_amd.loader.js */3);
amdRequire.config = function() {/* config is ignored, use webpack options */};
module.exports = amdRequire;


/******/},
/******/
/******/3: function(module, exports, require) {

/**! (webpack)\buildin\__webpack_options_amd.loader.js!(webpack)\buildin\__webpack_options_amd.loader.js !**/

/* empty to return {} */

/******/}
/******/})
```

# js/1.output.js

``` javascript
/******/webpackJsonp(1,{
/******/4: function(module, exports, require) {

/**! (webpack)\examples\require.context\templates !**/

/***/	var map = {"./a.js":5,"./b.js":6,"./c.js":7};
/***/	exports = module.exports = function(name) {
/***/		return require(exports.id(name) || name)
/***/	};
/***/	exports.id = function(name) {
/***/		return map[name] || map[name+".js"];
/***/	};
/***/	exports.keys = function() {
/***/		return Object.keys(map);
/***/	};

/******/},
/******/
/******/5: function(module, exports, require) {

/**! (webpack)\examples\require.context\templates\a.js !**/

module.exports = function() {
	return "This text was generated by template A";
}

/******/},
/******/
/******/6: function(module, exports, require) {

/**! (webpack)\examples\require.context\templates\b.js !**/

module.exports = function() {
	return "This text was generated by template B";
}

/******/},
/******/
/******/7: function(module, exports, require) {

/**! (webpack)\examples\require.context\templates\c.js !**/

module.exports = function() {
	return "This text was generated by template C";
}

/******/}
/******/})
```

# Info

## Uncompressed

```
Hash: bf0ce807e0d159bd6a3739abefcc2e57
Compile Time: 45ms
Chunks: 2
Modules: 8
Modules including duplicates: 8
Modules first chunk: 4
main     output.js:     3870 chars/bytes
       1.output.js:     1110 chars/bytes

 <id>    <size>  <filename>
       <reason> from <filename>
output.js
    0       295  .\example.js
       main
    1       502  (webpack)\buildin\__webpack_console.js
       require (2x) from .\example.js
    2       502  (webpack)\buildin\__webpack_amd_require.js
       require (1x) from .\example.js
    3        24  (webpack)\buildin\__webpack_options_amd.loader.js!(webpack)\buildin\__webpack_options_amd.loader.js
       require (1x) from (webpack)\buildin\__webpack_amd_require.js
1.output.js
    4       322  [context] (webpack)\examples\require.context\templates
       async context from .\example.js
    5        80  (webpack)\examples\require.context\templates\a.js
       async context from .\example.js
    6        80  (webpack)\examples\require.context\templates\b.js
       async context from .\example.js
    7        80  (webpack)\examples\require.context\templates\c.js
       async context from .\example.js
```

## Minimized (uglify-js, no zip)

```
Hash: 1340b9e7d018a9c04cbe2e165e1d6f22
Compile Time: 288ms
Chunks: 2
Modules: 8
Modules including duplicates: 8
Modules first chunk: 4
main     output.js:     1405 chars/bytes
       1.output.js:      456 chars/bytes

 <id>    <size>  <filename>
       <reason> from <filename>
output.js
    0       186  .\example.js
       main
    1       403  (webpack)\buildin\__webpack_console.js
       require (2x) from .\example.js
    2       271  (webpack)\buildin\__webpack_amd_require.js
       require (1x) from .\example.js
    3         0  (webpack)\buildin\__webpack_options_amd.loader.js!(webpack)\buildin\__webpack_options_amd.loader.js
       require (1x) from (webpack)\buildin\__webpack_amd_require.js
1.output.js
    4       213  [context] (webpack)\examples\require.context\templates
       async context from .\example.js
    5        73  (webpack)\examples\require.context\templates\a.js
       async context from .\example.js
    6        73  (webpack)\examples\require.context\templates\b.js
       async context from .\example.js
    7        73  (webpack)\examples\require.context\templates\c.js
       async context from .\example.js
```

## Graph

![webpack-graph](http://webpack.github.com/webpack/examples/code-splitted-require.context-amd/graph.svg)