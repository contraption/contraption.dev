---
title: Collections
description: A PHP collections component using optimal data structures
extends: _layouts.documentation
section: content
---

# Collections

The Collections component provides a fluent wrapper for working with different sets of data. Each collection uses a 
data-structure provided by the [Data Structures extension for PHP](https://www.php.net/manual/en/book.ds.php), instead of
an array.

## Installation

This package depends on [ext-ds](https://www.php.net/manual/en/ds.installation.php), so you will need to install that 
first. The easiest way is using pecl.
                        
```
pecl install ds
```

This package is bundled with the standard Contraption framework, but if you wish to use the component outside of the
framework, you can install it using composer.

```
composer require contraption/collections
```

## Usage

There are four main collections provided by this component. They are the map, sequence, queue and stack.

### Map

A map is a collection of key-value pairs, and functions almost identically to an array. The key can be any type, even objects,
but must be unique.

You can create a new map by instantiating the following class.

```
\Contraption\Collections\Map
```

Alternatively you can use the `Contraption\Collections\Collections` helper class.

```php
$map = Collections::map([
    'key1' => 'value1',
    'key2' => 'value2'
]);
```

[Read more here](/docs/collections/maps)

#### Immutable Variation

There is an immutable version of the map collection `\Contraption\Collections\ImmutableMap`. You can create a new
instance of this class, as well as using the `Collections::immutableMap()` method on the collections helper. A
`LogicException` is thrown if you attempt to modify the collection.

> Tip: You can turn a mutable map into an immutable by calling the `immutable()` method.

### Sequence

A sequence is a collection of values arranged in a single dimension, similar to a List found in other languages. It 
functions almost identically to an array using incremental integer keys, with the following exceptions;

- Values will always be indexed as `[0, 1, 2, …, size - 1]`.
- Removing or inserting updates the position of all successive values.
- Only allowed to access values by index in the range `[0, size - 1]`.
 
You can create a new sequence by instantiating the following class.

```
\Contraption\Collections\Sequence
```

Alternatively you can use the `Contraption\Collections\Collections` helper class.

```php
$map = Collections::sequence([
    'value1', 'value2'
]);
```

[Read more here](/docs/collections/sequences)

#### Immutable Variation

There is an immutable version of the sequence collection `\Contraption\Collections\ImmutableSequence`. You can create a new
instance of this class, as well as using the `Collections::immutableSequence()` method on the collections helper. A
`LogicException` is thrown if you attempt to modify the collection.

> Tip: You can turn a mutable sequence into an immutable by calling the `immutable()` method.

### Queue

A queue is a first in, first out collection that only allows access to the value at the front of the queue. It iterates
over the values destructively, so each time you retrieve an item it is removed from the collection.

You can create a new queue by instantiating the following class.

```
\Contraption\Collections\Queue
```

Alternatively you can use the `Contraption\Collections\Collections` helper class.

```php
$map = Collections::queue([
    'value1', 'value2'
]);
```

[Read more here](/docs/collections/queues)

### Stack

A Stack is similiar to a Queue, but is last in, first out, only allowing access to the value at the top of the stack.

You can create a new stack by instantiating the following class.

```
\Contraption\Collections\Stack
```

Alternatively you can use the `Contraption\Collections\Collections` helper class.

```php
$map = Collections::stack([
    'value1', 'value2'
]);
```

[Read more here](/docs/collections/stacks)