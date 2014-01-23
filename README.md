## Terry-Mao/goconf

`Terry-Mao/goconf` is an configuration file parse module.

## Requeriments
* Go 1.2 or higher

## Installation

Just pull `Terry-Mao/goconf` from github using `go get`:

```sh
# download the code
$ go get -u github.com/Terry-Mao/goconf
```

## Usage

```go
package main                                                                   
                                                                               
import (                                                                       
    "fmt"                                                                      
    "github.com/Terry-Mao/goconf"                                              
)                                                                              
                                                                               
func main() {                                                                  
    conf := goconf.New()                                                       
    if err := conf.Parse("./examples/conf_test.txt"); err != nil {             
        panic(err)                                                             
    }                                                                          
    core := conf.Get("core")                                                   
    if core == nil {                                                           
        panic("no core section")                                               
    }                                                                          
    id, err := core.Int("id")                                                  
    if err != nil {                                                            
        panic(err)                                                             
    }                                                                          
    fmt.Println(id)                                                            
} 
```

## Examples

```sh
# configuration examples
# this is comment, goconf will ignore it.

# this is the section name
[core]

# a key-value config which key is test and value is 1
test = 1

# one mb
test1 = 1mb

# one second
test2 = 1s

# boolean
test3 = true
```

## Documentation

Read the `Terry-Mao/goconf` documentation from a terminal

```go
$ godoc github.com/Terry-Mao/goconf -http=:6060
```

Alternatively, you can [goconf](http://go.pkgdoc.org/github.com/Terry-Mao/goconf) online.
