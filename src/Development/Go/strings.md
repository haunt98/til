# [strings](https://golang.org/pkg/strings/)

Replace list of strings by using Replacer:

```go
template := "My city is {city} and my country is {country}"
r := strings.NewReplacer("{city}", "Sai Gon", "{country}", "Viet Nam")
fmt.Println(r.Replace(template))
```
