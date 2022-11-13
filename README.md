TreeMap
=======

Fork of github.com/igrmk/treemap

`TreeMap` is a generic key-sorted map using a red-black tree under the hood.
It requires and relies on [Go 1.18](https://tip.golang.org/doc/go1.18) generics feature.
Iterators are designed after C++.

### Usage

```go
package main

import (
	"fmt"

	"github.com/igrmk/treemap/v2"
)

func main() {
	tr := treemap.New[int, string]()
	tr.Set(1, "World")
	tr.Set(0, "Hello")
	for it := tr.Iterator(); it.Valid(); it.Next() {
		fmt.Println(it.Key(), it.Value())
	}
}

// Output:
// 0 Hello
// 1 World
```

### Install

```bash
go get github.com/psilva261/treemap/v2
```

### Complexity

|              Name              |   Time    |
|:------------------------------:|:---------:|
|             `Set`              | O(log*N*) |
|             `Del`              | O(log*N*) |
|             `Get`              | O(log*N*) |
|           `Contains`           | O(log*N*) |
|             `Len`              |   O(1)    |
|            `Clear`             |   O(1)    |
|            `Range`             | O(log*N*) |
|           `Iterator`           |   O(1)    |
|           `Reverse`            | O(log*N*) |
| Iterate through the entire map |  O(*N*)   |

### Memory usage

TreeMap uses O(*N*) memory.

### Licensing

Copyright &copy; 2022 igrmk.
This work is free. You can redistribute it and/or modify it under the
terms of the Unlicense. See the LICENSE file for more details.
