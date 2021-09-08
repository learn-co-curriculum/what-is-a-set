# Day 5: What Is a Set?

## Learning Goals

- Define the characteristics of a set
- Implement a common methods of a set class

## Introduction

A **set** is a data structure that can store any number of _unique_ values or
elements. That means there are _no repeating elements_ in a set.

Many languages provide sets as part of the core language, but today, we'll be
building our own `MySet` class by using a hash/object as the underlying data
structure. We've chosen a hash/object because that data structure only allows
unique keys.

```txt
// Convert an Array to a Set

array = [1, 3, 1, 2]
set = new Set from array
=> {1, 3, 2}
```

## Implement the MySet class

We have already declared a class called `MySet` in the starter files and
provided the underlying data structure: a hash/object called `data`. You'll need
to build out all of the methods. Do not worry about the ordering of items in the
set. They can be in any order.

Be aware that these methods may go by different names in different languages.
This is one way to implement a set, there are others! We are basing ours on
JavaScript's `Set` class.

### Initialization, e.g. `constructor(iterable)` or `#initialize(iterable)`

We should be able to initialize a new `MySet` instance with no data, or by
providing an iterable, such as an array or string. When a new `MySet` instance
is initialized with an array or string, only its **unique** contents should be
added to the `MySet` instance.

Use a value of `true` for each key: `{ dog: true }`.

```txt
new MySet()
=> MySet data = {}
new MySet([1, 2, 1, 3])
=> MySet data = { 1: true, 2: true, 3: true }
new MySet('hello')
=> MySet data = { 'h': true, 'e': true, 'l': true, 'o': true }
```

An error should be thrown if a user tries to initialize a new `MySet` instance
with anything other than nothing, a string, or an array.

### `size`

Returns the number of items in the MySet instance.

### `add(item)`

Add an item to a `MySet` instance. Remember, **only unique items** should exist
in `MySet`. When adding an item, the item is added as is. Return the `MySet`
instance.

```txt
my_set = new MySet()
my_set.add('caat')
=> MySet data = { 'caat' }

next_set = new MySet('doooog')
next_set.add('caarp')
=> MySet data = { 'd', 'o', 'g', 'caarp' }
next_set.add(12)
=> MySet data = { 'd', 'o', 'g', 'caarp', 12 }
```

**_Note on JS: Arrays cannot be keys for JS objects. They will be converted to
strings by default like so: `[1, 2] => '1,2'`. Don't worry about this. We'll
ensure our tests allow for this. For now, just be aware that actual Sets most
certainly can handle Arrays!_**

### `delete(item)`

Removes the item from the set. If the removal was successful, return `true`. If
the item was not removed (i.e. if the item was not present in the set to begin
with), return `false`.

```txt
my_set = new MySet('aabb')
my_set.delete('a')
=> true
my_set.delete('z')
=> false
```

**_Note on JS: Don't worry about handling Arrays here!_**

### `has(item)`

If the item is in the `MySet` instance, return `true`, otherwise `false`.

**_Note on JS: Don't worry about handling Arrays here!_**

### `entries`

Returns an array containing all of the values in the `MySet` instance.

```txt
my_set = new MySet('aabb')
my_set.entries()
=> ['a', 'b']
```

**_Note on JS: Don't worry about handling Arrays (which were meant to be keys in
`this.data`) here!_**

Use the language of your choosing. We've included starter files for some
languages where you can pseudocode, explain your solution and code.

**_And remember, don't run our tests until you've passed your own!_**

## How to run your own tests

### Ruby

1. `cd` into the ruby folder
2. `ruby <filename>.rb`

### JavaScript

1. `cd` into the javascript folder
2. `node <filename>.js`

## How to run our tests

### Ruby

1. `cd` into the ruby folder
2. `bundle install`
3. `rspec`

### JavaScript

1. `cd` into the javascript folder
2. `npm i`
3. `npm test`
