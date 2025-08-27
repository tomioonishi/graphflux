graphflux is a JavaScript library for creating and modifying directed and undirected graphs. In addition to a core graph API, it also comes with implementations for many common graph algorithms.

# Table of Contents

- [Example](#example)
- [Installing](#installing)
  - [npm Install](#npm-install)
  - [Bower Install](#bower-install)
  - [Browser Scripts](#browser-scripts)
  - [Source Build](#source-build)
- [[API Reference]]
- [Bug Tracking](/johntech0828/graphflux/issues)
- [[Contributing]]
- [License](#license)

## Example

This following code block shows a small example of how to use graphflux in node.js:

```js
var Graph = require("graphflux").Graph;

// Create a new directed graph
var g = new Graph();

// Add node "a" to the graph with no label
g.setNode("a");

g.hasNode("a");
// => true

// Add node "b" to the graph with a String label
g.setNode("b", "b's value");

// Get the label for node b
g.node("b");
// => "b's value"

// Add node "c" to the graph with an Object label
g.setNode("c", { k: 123 });

// What nodes are in the graph?
g.nodes();
// => `[ 'a', 'b', 'c' ]`

// Add a directed edge from "a" to "b", but assign no label
g.setEdge("a", "b");

// Add a directed edge from "c" to "d" with an Object label.
// Since "d" did not exist prior to this call it is automatically
// created with an undefined label.
g.setEdge("c", "d", { k: 456 });

// What edges are in the graph?
g.edges();
// => `[ { v: 'a', w: 'b' },
//       { v: 'c', w: 'd' } ]`.

// Which edges leave node "a"?
g.outEdges("a");
// => `[ { v: 'a', w: 'b' } ]`

// Which edges enter and leave node "d"?
g.nodeEdges("d");
// => `[ { v: 'c', w: 'd' } ]`
```

or graphflux can be included in a webpage:

```html
<script src="http://PATH/TO/graphflux.min.js"></script>
 <script>
var g = new graphflux.Graph();
// ...etc.
```

## Installing

### npm Install

Before installing this library you need to install the [npm package manager](http://npmjs.org/).

To get graphflux from npm, use:

    $ npm install graphflux

### Source Build

Before building this library you need to install the [npm package manager](http://npmjs.org/).

Check out this project and run this command from the root of the project:

    $ make dist

This will generate `graphflux.js` and `graphflux.min.js` in the `dist` directory
of the project.

# License

graphflux is licensed under the terms of the MIT License. See the [LICENSE](LICENSE) file for details.

[npm package manager]: http://npmjs.org/
