# Sets
## A. What It Is

In Python, sets are exactly like lists except for the fact that their elements are immutable -- which means that you can't change or 'mutate' (this is where immutable comes from) an element of a set once declared. Of course, you can still add and remove from the set.

An interesting part of a set, and often one of its defining characteristics, is that a set can store multiple data types. A set containing a number, a string, a tuple, and a dictionary all at the same time is not uncommon.

Additionally, sets do not keep track of the order of the data, nor can they hold duplicate values. This makes sets very efficient, with common operations like adding, removing, and checking presence can be done with O(1) efficiency.

## B. How They Work

A set, unlike our previous queue example, is actually completely baked into Python! To make a set, you simply have to use curly braces, like so:
```python
set = {"This", "is", "a", "set"}
```
That said, if you were to `print(set)`, the current group of words would be displayed in a random order. This is due to the fact that, as mentioned before, sets do not retain order *at all*.

#### i. Unions

The union method returns a set that contains all items from the original set, and all items from the specified set(s).

You can specify how many sets you want, separated by commas. It does not have to be a set; it can be any iterable object. Of course, if an item is present in more than one set, the result will contain only one appearance of this item.

```python
x = {"a", "b", "c"}
y = {"a", "d", "e"}
z = {"c", "d", "f"}

result = x.union(y, z)

print(result) # {"a", "b", "c", "d", "e", "f"} <-- again, this order is randomized
```

#### ii. Intersection

The intersection method returns a set that contains the overlap between two or more sets.

In other words, the returned set contains only items that exist in both sets, or in all sets if the comparison is done with more than two sets.

```python
x = {"a", "b", "c"}
y = {"c", "d", "e"}
z = {"f", "g", "c"}

result = x.intersection(y, z)

print(result) # {"c"}
```
## C. Performance
|Common Set Operation|Description|Performance (assuming good conflict resolution)|
|:-:|:-:|:-:|
|add(value)|Adds "value" to the set|O(1)|
|remove(value)|Removes the "value" from the set|O(1)|
|member(value)|Determines if "value" is in the set|O(1)|
|size()|Returns the number of items in the set|O(1)|

## D. Examples

Here are three sets that each hold 1 character long strings.

```python
x = {"a", "b", "c", "d", "e"}
y = {"c", "d", "e", "f", "g"}
z = {"e", "f", "g", "h", "i"}
```

Lets find the intersection between the sets.

```python
result = x.intersection(y, z)
print(result)  # {"e"}
```

Now lets add "f" and try again

```python
x.add("f")

result = x.intersection(y, z)
print(result)  # {"e", "f"}
```

[Back to Welcome Page](0-welcome.md)