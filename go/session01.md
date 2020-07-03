# GoLang basics

## Language

- Is statically typed
- Is garbage collected
- Is statically compiled
- Is object oriented
- Is concurrency friendly

## Go commands

```
go
go fmt
go doc fmt | less
go doc math Sqrt
go env
```

## Go environment variables

- GOPATH
- GOOS
- GOARCH

## Go format

- Tabs for indentation
- C++ / Java comments
- Lower case for package names
- mixedCaps or MixedCaps instead of underscores
- Go uses semicolons like C++ / Java, but the lexer adds them automatically so you don't have to

Just run `go fmt`

https://github.com/golang/go/wiki/CodeReviewComments
https://github.com/bahlo/go-styleguide

---

## Types

- bool 
- string
- rune
- byte
- int, int8,  int16,  int32,  int64
- uint, uint8, uint16, uint32, uint64
- uintptr
- float32
- float64
- complex64, complex128

#### Zero values

bool: false
numeric: 0
string: ""

### Structs

```
type V struct {
    X, Y int 
}

v1 := V{}
v2 := V{ 2, 2 }
v3 := V{ Y: 3 }
```

### Arrays and Slices

#### Arrays

```
var a [10]int
```

#### Slices

```
var a []int
s := []int {1, 2, ,3, 4 , 5}
s = append(s, 6)
```

#### len() and cap()

### Type conversion

newVar := Type(variable)

## Pointers

```
var p *int
i := 42

// get pointer
p = &i

// Dereferring
*p = 21
s := i+*p
```

