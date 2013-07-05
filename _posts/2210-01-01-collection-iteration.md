--- 
category: api
heading: Collection Iteration
---

#### [each(fn, \[context\])](/api/each/)
_alias: forEach(fn, \[context\])_

Call the iterator function for each element in the collection and return the collection.

#### [map(fn, \[context\])](/api/map/)

Call the iterator function for each element in the collection. For any elements returned by the iterator function, return them wrapped in a new collection.

#### [sort(fn)](/api/sort/)

Re-order the elements in the collection based on the sort function.

#### [pluck(propertyType, \[attr\])](/api/pluck/)

Return an array of values from each element in the collection - e.g. attribute, data or object properties.

#### [select(filter)](/api/select/)

Return a new collection of elements that match the filter, which can be a function, CSS selector or elements.

#### [every(filter)](/api/every/)

Return `true` if **all** elements in the collection match the filter, which can be a function, CSS selector or elements. Otherwise `false`.

#### [some(filter, \[context\])](/api/some/)
_alias: is(filter, \[context\])_

Return `true` if **any** elements in the collection match the filter, which can be a function, CSS selector or elements. Otherwise `false`.

#### [indexOf(filter)](/api/indexOf/)
_alias: lastIndexOf(filter)_

Return the collection index of the first element in the collection that matchs the filter, which can be a function, CSS selector or elements. Otherwise `-1`.
