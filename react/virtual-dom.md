# Virtaul DOM

The Virtual DOM is in charge of scheduleing the rendering and updating of the
actual DOM. This process is called
[reconciliation](https://reactjs.org/docs/reconciliation.html). Since updating
the DOM is an expensive operation, using Javascript to find out if we actually
need to update can lead to performance gains.

This concept is not unique to React, many other Frontened JS frameworks have a
virtual DOM. If you want to really understand the internals, [here is a great
post](https://medium.com/@deathmood/how-to-write-your-own-virtual-dom-ee74acc13060)
about building your own Virtual DOM. It's surprisingly easy to get to a naive
implementation and will really help you understand what is giong on under the
hood.
