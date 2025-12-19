# Class 'timeInterval'

An object from class `"timeInterval"` represents a time interval or an
union of time intervals. Methods are defined for union, intersection,
complement and other suitable operations.

## Objects from the Class

Objects can be created by calls of the form `new("timeInterval", ...)`
or, preferably,
[`timeInterval`](https://geobosh.github.io/timeDateDoc/reference/timeInterval-methods.md).

A `"timeInterval"` object represents the union of zero or more intervals
of the form `[left, right)`, i.e., closed on the left and open on the
right (but see below the note about `left = -Inf`). The internal
representation is always in a canonical disjoint form, such that the
intervals do not overlap and do not touch at their end points.

The start of an interval can be `-Inf` and the end can be `Inf`. When
the left side of an interval is `-Inf`, it is currently unspecified if
`-Inf` belongs to it. In other words, it is not defined whether
`timeInterval[-Inf, b]` represents \\(-\infty, b)\\ or \\\[-\infty,
b)\\. Feedback on this will be appreciated. The current code treats it
as \\\[-\infty, b)\\.

## Slots

- `left`::

  Object of class `"timeDate"` \~~

- `right`::

  Object of class `"timeDate"` \~~

## Methods

- initialize:

  `signature(.Object = "timeInterval")`: ...

- timeInterval:

  `signature(left = "timeInterval", right = "missing")`: ...

- show:

  `signature(object = "timeInterval")`: ...

- %in_int%:

  `signature(x = "timeDate", ti = "timeInterval")`: ...

- %in_int%:

  `signature(x = "timeInterval", ti = "timeInterval")`: ...

- &:

  `signature(e1 = "timeInterval", e2 = "timeInterval")`: ...

- ^:

  `signature(e1 = "timeInterval", e2 = "timeInterval")`: ...

- \|:

  `signature(e1 = "timeInterval", e2 = "timeInterval")`: ...

## Author

Georgi N. Boshnakov

## See also

[`timeInterval`](https://geobosh.github.io/timeDateDoc/reference/timeInterval-methods.md)
for creation of `"timeInterval"` objects and further examples,

[`in_int`](https://geobosh.github.io/timeDateDoc/reference/in_int.md)
for set operations on `"timeInterval"` objects
