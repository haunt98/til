# [sync](https://golang.org/pkg/sync/)

Use `Mutext` to prevent accessing variable from different goroutine at the same time:

```go
type foo struct {
    mu sync.Mutext

    bar map[string]string
}

func (f *foo) doSomething {
    f.mu.Lock()
    defer f.mu.Unlock()

    // do the thing
}

```

Use `RWMutex` if there are many readers, and few writers:

```go
type foo struct {
    mu sync.RWMutext

    bar map[string]string
}

func (f *foo) read {
    f.mu.RLock()
    defer f.mu.RUnlock()

    // read
}

func (f *foo) write {
    f.mu.Lock()
    defer f.mu.Unlock()

    // write
}
```
