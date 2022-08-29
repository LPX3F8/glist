# glist
👨‍💻‍ based on golang native container/list, support generics

# Install
- go version >= 1.18
```bash
go get -u github.com/LPX3F8/glist
```
# Example
```go
import (
	"fmt"

	"github.com/LPX3F8/glist"
)

type foo struct {
	V string
}

func (o *foo) Print() {
	fmt.Println(o.V)
}

func main() {
	fooList := glist.New[*foo]()
	fooList.PushBack(&foo{V: "1"})
	fooList.PushBack(&foo{V: "2"})
	fooList.PushBack(&foo{V: "3"})
	fmt.Println(fooList.Len())
	for e := fooList.Front(); e != nil; e = e.Next() {
		e.Value.Print()
	}
}
```