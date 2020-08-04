# [time](https://golang.org/pkg/time/)

To parse string to time in golang, must define layout first.

Read default layouts in [Constants](https://golang.org/pkg/time/#pkg-constants).

The reference time:

```txt
Mon Jan 2 15:04:05 MST 2006
```

To define your layout, rewrite reference time in your layout.

Example `time.Parse` from `string` to `time.Time`:

```go
layout := "2006-01-02 15:04:05"

t, err := time.Parse(layout, "2020-06-09 23:04:02")
if err != nil {
    log.Fatal(err)
}

fmt.Println(t)
```

Example `time.ParseInLocation` from `string` to `time.Time` with location:

```go
layout := "2006-01-02 15:04:05"

loc, err := time.LoadLocation("Asia/Ho_Chi_Minh")
if err != nil {
    log.Fatal(err)
}

t, err := time.ParseInLocation(layout, "2020-06-09 23:04:02", loc)
if err != nil {
    log.Fatal(err)
}

fmt.Println(t)
```

Example `Format` from `time.Time` to `string`:

```go
now := time.Now()

layout := "2006-01-02"
fmt.Println(now.Format(layout))
```

Example `Format` from `time.Time` to `string` with location:

```go
loc, err := time.LoadLocation("Asia/Ho_Chi_Minh")
if err != nil {
    return "", err
}

now := time.Now().In(loc)

layout := "2006-01-02"
fmt.Println(now.Format(layout))
```

Example `time.Unix` from timestamp ms to `time.Time`:

```go
time.Unix(0, timestamp * int64(time.Millisecond))
```
