# grunt-jsmin-sourcemap [![Build status](https://travis-ci.org/twolfson/grunt-jsmin-sourcemap.png?branch=master)](https://travis-ci.org/twolfson/grunt-jsmin-sourcemap)

Grunt task for JSMin and source maps.

## Synopsis
[Grunt](https://github.com/gruntjs/grunt/) is a node.js based CLI build tool.

[JSMin](http://www.crockford.com/javascript/jsmin.html) is a JavaScript minifier that removes whitespace and comments.

[Source maps](http://www.html5rocks.com/en/tutorials/developertools/sourcemaps/) enables developers to view and interact with minified JavaScript as if it were unminified (providing useful line errors and easier debugging).

When you combine all three of these, you get a grunt plugin that is your new best debugging friend.

## Demos
The demos in the [node-jsmin-sourcemap](https://github.com/twolfson/node-jsmin-sourcemap), what makes this tick, are hosted on Plunker for your testing and enjoyment.

- Basic [http://embed.plnkr.co/mGHUpe](http://embed.plnkr.co/mGHUpe)
- jQuery [http://embed.plnkr.co/JyNn5e](http://embed.plnkr.co/JyNn5e)
- Multi [http://embed.plnkr.co/FPkQx6](http://embed.plnkr.co/FPkQx6)

## Getting Started
Install this grunt plugin next to your project's [grunt.js gruntfile][getting_started] with: `npm install grunt-jsmin-sourcemap`

Then add this line to your project's `grunt.js` gruntfile:

```javascript
grunt.loadNpmTasks('grunt-jsmin-sourcemap');
```

[grunt]: https://github.com/cowboy/grunt
[getting_started]: https://github.com/cowboy/grunt/blob/master/docs/getting_started.md

## Documentation
`grunt-jsmin-sourcemap` is registered under the `jsmin-sourcemap` task. Your initConfig should look similar to this:
```js
grunt.initConfig({
  'jsmin-sourcemap': {
    all: {
      // Source files to concatenate and minify (also accepts a string and minimatch items)
      src: ['public/js/jquery.js', 'public/js/underscore.js'],

      // Destination for concatenated/minified JavaScript
      dest: 'dist/js/all.min.js',

      // Destination for sourcemap of minified JavaScript
      destMap: 'dist/js/all.js.map',

      // Optional root for all relative URLs
      srcRoot: 'some/lower/directory',

      // Optional cwd to resolve from for all URLs
      // Converts jquery.js -> some/higher/directory/jquery.js during lookup but mapping preserves jquery.js in map file
      cwd: 'some/higher/directory',

      options: {
        // Whether to create sourcemaps for the file(s)
        createSourceMaps: true
      }

    },

    // Compact format is also accepted
    'dest/file.js': ['src/file1.js', 'src/file2.js']
  }
});
```

In some cases, you may want to *only* concatenate and minify the files without creating a source map for them. Use the setting `options.createSourceMaps` (default: `true`) to configures this.

## Contributing
In lieu of a formal styleguide, take care to maintain the existing coding style. Add unit tests for any new or changed functionality. Lint via [grunt][grunt] and test via `npm test`.

## Donating
Support this project and [others by twolfson][gittip] via [gittip][].

[![Support via Gittip][gittip-badge]][gittip]

[gittip-badge]: https://rawgithub.com/twolfson/gittip-badge/master/dist/gittip.png
[gittip]: https://www.gittip.com/twolfson/

## License
As of Dec 05 2013, Todd Wolfson has released this repository and its contents to the public domain.

It has been released under the [UNLICENSE][].

[UNLICENSE]: UNLICENSE

Previous to this, it was licensed under the [MIT license][].

[MIT license]: https://github.com/twolfson/grunt-jsmin-sourcemap/blob/4ebd0957a440bc97cb55e8178c3f0d7cfaf6ee43/README.md#license
