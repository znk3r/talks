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

https://gist.github.com/asukakenji/f15ba7e588ac42795f421b48b8aede63

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

## Loops

```
// typical loop
for i:=0; i < 100; i++ {}

// while sum<100 equivalent
for sum < 100 {}

// infinite loop
for {}

// loop array for-each
for i, v := range myList {}
```

## Conditionals

### if
```
if i<10 {

} else {

}
```

#### if scope

```
if err := DoSomething(); err != nil {
    fmt.Println(err)
}
```

### switch
```
        switch os := runtime.GOOS; os {
        case "darwin":
            fmt.Println("OS X.")
        case "linux":
            fmt.Println("Linux.")
        default:
            // freebsd, openbsd,
            // plan9, windows...
            fmt.Printf("%s.\n", os)
        }
```

## Functions

```
func swap1(x, y string) (string, string) {
	return y, x
}

func swap2(x, y string) (a, b string) {
	a = y
    b = x
	return
}
```

## Methods

### Pointer vs Value receivers

```
func (p Coordinates) Abs() float64 {}
func (p *Coordinates) Add(a Coordinates) {}
```

## Interfaces

```
type Abser interface {
    Abs() float64 
}
```

### Stringer

```
type Person struct {
	Name string
	Age  int
}

func (p Person) String() string {
	return fmt.Sprintf("%v (%v years)", p.Name, p.Age)
}

a := Person{"Arthur Dent", 42}
fmt.Println(a)
```

