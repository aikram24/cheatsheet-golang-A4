# awesome-golang-syntax
<a href="https://github.com/DennyZhang?tab=followers"><img align="right" width="200" height="183" src="https://raw.githubusercontent.com/USDevOps/mywechat-slack-group/master/images/fork_github.png" /></a>

[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](http://makeapullrequest.com) [![LinkedIn](https://raw.githubusercontent.com/USDevOps/mywechat-slack-group/master/images/linkedin.png)](https://www.linkedin.com/in/dennyzhang001) <a href="https://www.dennyzhang.com/slack" target="_blank" rel="nofollow"><img src="http://slack.dennyzhang.com/badge.svg" alt="slack"/></a> [![Github](https://raw.githubusercontent.com/USDevOps/mywechat-slack-group/master/images/github.png)](https://github.com/DennyZhang)

File me [tickets](https://github.com/DennyZhang/awesome-golang-syntax/issues) or star [the repo](https://github.com/DennyZhang/awesome-golang-syntax).

See more CheatSheets from Denny: [here](https://github.com/topics/denny-cheatsheets)

Table of Contents
=================

   * [awesome-golang-syntax](#awesome-golang-syntax)
      * [Array](#array)
      * [Compact Coding](#compact-coding)
      * [String](#string)
      * [Integer](#integer)
      * [Dict &amp; Set](#dict--set)
      * [Goroutines](#goroutines)
      * [Bit Operator](#bit-operator)
      * [Math](#math)
      * [queue/heapq](#queueheapq)
   * [Code snippets](#code-snippets)
   * [More links](#more-links)

<a href="https://www.dennyzhang.com"><img align="right" width="185" height="37" src="https://raw.githubusercontent.com/USDevOps/mywechat-slack-group/master/images/dns_small.png"></a>

**Golang CheatSheet**: https://github.com/DennyZhang/cheatsheet-golang-A4

## Syntax Sugar: From Python To Golang
| Name              | Python                  | Golang                                                   |
| :---------------- | ----------------------- | -------------------------------------------------------- |
| sum slice         | `sum([1, 2, 3])`        | `sum := 0; for i := range nums { sum += nums[i] }`       |
| Get last item     | `nums[-1]`              | `nums[len(nums)-1]`                                  |
| For               | `for i in range(10):`   | `for i := 0; i < 10; i++`                                |
| Loop string       | `for ch in str:`        | `for _, ch := range str { fmt.Print(ch) }`               |
| Iterator          | `for num in nums:`      | `for _, num := range nums {fmt.Print(num)}`              |
| While             | `while isOK:`           | `for isOK`                                               |
| Reverse list      | `nums[::-1]`            | Need to create your own function. Weird!                 |
| Get min           | `min(2, 6, 5)`        |                                                          |

## Golang Compact Coding

| Name                                | Comment                                     |
| :---------------------------------- | -----------------------------------------   |
| Declare variables with initializers | `var ischecked, v, str  = false, 2, "yes!"` |
| One line if statement               | `if a >= 1 { fmt.Print("yes") }`            |

## Array

| Name                            | Comment                                       |
| :-----------------------------  | --------------------------------------------  |
| Make a array                    | `var a [2]string; a[0]="hello"; a[1]="world"` |
| Create array with given values  | `T := [6]int{2, 3, 7, 5, 11, 13}`          |
| Create array with given values  | `T := []string{"a", "c", "b", "d"}`           |
| Create dynamically-sized arrays | `a := make([]int, 5)`                         |
| Create dynamically-sized arrays | `a := make([]int, 1, 5)` // 5 is capacity     |
| Sort array                      | `sort.Strings(T); fmt.Print(T)`               |
| Append item                     | `T = append(T, "e")`                          |
| Append items                    | `T = append(T, "e", "b", "c")`                |
| Remove last itme                | `T = T[:len(T)-1]`                            |
| Slices of a array               | `var T2 = T[1:3]` // Notice: it's a reference |
  
## String

| Name                      | Comment                                              |
| :------------------------ | ---------------------------------------------------- |
| Format string             | `fmt.Sprintf("at %v, %s", e.When, e.What)`           |
| Split string              | `var L = strings.Split("hi,golang", ",")`            |
| Replace string            | `var str2 = strings.Replace("hi,all", ",", ";", -1)` |
| String to int             | `i, _ := strconv.Atoi("39038")`                      |
| Convert string to float   | `f, _ := strconv.ParseFloat("3.1415", 64)`           |
| Convert string to int     | `i, _ := strconv.ParseInt("12345", 10, 64)`          |
| Convert string to int     | `i, err := strconv.Atoi("-42")`                      |

## Integer

| Name          | Comment        |
| :------------ | -------------- |

## Dict & Set

| Name            | Comment                          |
| :-------------- | -------------------------------- |
| Create dict     | `map[string]int{"a": 1, "b": 2}` |
| Create dict     | `make(map[string]int)`           |
| Check existence | `_, ok := m[k]`                  |
| Delete key      | `delete(m, "k1")`                |
  
## Goroutines
| Name                   | Comment              |
| :--------------------- | -------------------- |
|                        |                      |

[example_goroutine.go](example_goroutine.go)

## Bit Operator

| Name           | Comment                       |
| :------------- | ----------------------------- |
| shift left     | `fmt.Print(1 << 10)` // 1024  |
| shift right    | `fmt.Print(1024 >> 3)` // 128 |

## File
| Name           | Comment          |
| :------------- | ---------------- |
  
## Math

| Name          | Comment                  |
| :------------ | ------------------------ |

## queue/heapq

| Name            | Comment                |
| :-------------- | ---------------------- |

# Code snippets
- Create 2D arrays
```
board := [][]string{
	[]string{"_", "_", "_"},
	[]string{"_", "_", "_"},
	[]string{"_", "_", "_"},
}
```

- Logging
```
import "github.com/op/go-logging"
log := logging.MustGetLogger("my-app")
log.Info("Some info...")
log.Warning("Some warning...")
log.Error("Some error!")
log.Critical("Some critical!")
```

- struct
```
type Point struct {
	X, Y int
}

var (
	v1 = Point{10, 8}
	v2 = Point{X: 1}  // Y would be 0
	v3 = Point{}      // Both X and Y is 0
	p  = &Point{10, 8} // reference: type *Point
)

func main() {
	fmt.Println(p, v1, v2, v3)
}
```

- Goroutines & Channels
```
// Goroutines
go func() {
  // do something
}
```

```
// Channels
c := make(chan T [, capacity ])
c <- t // blocks on unbuffered channels until another routine receives the value

d := <-c // blocks on unbuffered channels until another routine sends the value

close(c)
```

# More links
- [A Tour Of Go](https://tour.golang.org/list)
- [The Go Programming Language](https://golang.org/doc/)
- https://github.com/a8m/go-lang-cheat-sheet

TODO: Need to automatically generate pdf

License: Code is licensed under [MIT License](https://www.dennyzhang.com/wp-content/mit_license.txt).

<a href="https://www.dennyzhang.com"><img align="right" width="201" height="268" src="https://raw.githubusercontent.com/USDevOps/mywechat-slack-group/master/images/denny_201706.png"></a>

<a href="https://www.dennyzhang.com"><img align="right" src="https://raw.githubusercontent.com/USDevOps/mywechat-slack-group/master/images/dns_small.png"></a>
