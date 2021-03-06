# ractive.set()

Updates data and triggers a re-render of any mustaches that are affected (directly or indirectly) by the change. Any [observers](observers.md) of affected [keypaths](keypaths.md) will be notified.

A `change` [event](events.md) will be fired with `keypath` and `value` as arguments
(or `map`, if you set multiple options at once).

The `keypath` can also contain wildcards [pattern observers](observers.md#pattern-observers).
All matching keypaths will be set with the supplied values:

```js
ractive.on( 'selectAll', function(){
	ractive.set( 'items.*.selected', true );
} )
```
When setting an array value, ractive will reuse the existing DOM nodes for the new array, adding or removing
nodes as necessary. This can impact nodes with [transitions](Transitions.md). See
 [ractive.merge()](ractive.merge().md) for setting a new array value while retaining existing
nodes corresponding to individual array item values.

> ### ractive.set( keypath, value )
> Returns a `Promise` (see [Promises](Promises.md)) that will be called after the set operation
and any transitions are complete.

> > #### **keypath** *`String`*
> > The [keypath](keypaths.md) of the data we're changing, e.g. `user` or `user.name`
> > or `user.friends[1]` or `users.*.status`

> > #### **value**
> > The value we're changing it to. Can be a primitive or an object (or array), in which case dependants of *downstream keypaths* will also be re-rendered (if they have changed)


> ### ractive.set( map )
> Returns a `Promise` (see [Promises](Promises.md)) that will be called after the set operation
and any transitions are complete.

> > #### **map** *`Object`*
> > A map of `keypath: value` pairs, as above
