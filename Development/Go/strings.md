# [strings](https://golang.org/pkg/strings/)

Replace list of strings by using `Replacer`:

```go
template := "My city is {city} and my country is {country}"
r := strings.NewReplacer("{city}", "Sai Gon", "{country}", "Viet Nam")
fmt.Println(r.Replace(template))
```

Use `Builder` to **efficently** concat string:

```go
func oldConcat(strs ...string) string {
	var result string
	for _, str := range strs {
		result += str
	}
	return result
}

func newConcat(strs ...string) string {
	var sb strings.Builder
	for _, str := range strs {
		sb.WriteString(str)
	}
	return sb.String()
}
```

Use `EqualFold` for faster compare strings with upper, lower or mixed case:

```go
strings.EqualFold("Foo", "fOO")
```
