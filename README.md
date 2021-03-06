

# cssn

A CSS pre-processor, really simple to set up, sort of like [`cssnext`](http://cssnext.io/) used to
be.

Back when we were young, `cssnext` used to be pretty simple: you installed it, you ran it, it
worked. Nowadays, `cssnext` has evolved to build atop PostCSS, with lots of configuration coming
with.

I have nothing against that move. It's a lot more powerful and flexible, and overall I think it is
absolutely the right thing to do. But I have lots of projects, and they all need a default that's
pretty much what `cssnext` used to be. So what `cssn` does is pretty much that: use `cssnext` and
PostCSS with a default setup that matches what I need. It's a whole lot fewer direct dependencies
to worry about, and a way to centralise options I like (such as being safe out of the box when
minifying).

This is for you if you like these defaults and don't want to think too much about your CSS
pre-processing; if you prefer the flexibility and power stick to the full PostCSS stack!

## Installation

The usual:

    npm install --save cssn

## Usage

    cssn [options] <input> <output>

When `NODE_ENV` is set to `production`, it minifies and does not report errors; otherwise it does
not minify but reports errors. Due to this behaviour, it (currently) produces no source maps.

Options include:

* `-w`, `--watch`: enter watch mode

## API

You can use `cssn` as a library. It exports a single function (the default one). Call it with
`options` and a callback. The options (all of which are optional) are:

* `watch`: boolean, enter watch mode or not.
* `input`: input path, required.
* `output`: output path.

The callback will receive an error if there was one, just `null` otherwise, and the processed CSS.

## Global installation

You may install it globally if you wish to (with `npm install -g cssn`), it will just work.
