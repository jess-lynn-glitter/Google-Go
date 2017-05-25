# Google-Go

Google Go

Been around since 2009.

A programming language aimed at helping web developers build apps at Google's scale and Google's speed, with a focus on rock-solid performance and ease of use, rather than chasing after the latest fads in programming.

Similar to C or C++

Why Google uses go:
It allows complex operations across multiple services to run concurrently, so a search can be working with Web, image, and video goroutines, bringing in results from them all and delivering them in one function return. The resulting code is faster and more robust: If one search channel doesn’t respond, you can open another. 


Good PDF overview:  http://core0.staticworld.net/assets/media-resource/73073/ifw_dd_2015_7_google_go.pdf

# Here is some basic code

```
package main

import (
	"fmt" //package imports - short for format
	"math"
)

func add(x int, y int) int { // can also shorten to (x, y int)
	return x + y
}

//variable declerations use type
var jo, mess, love bool //variables declared without an explicit initial value are given their zero value

// if statement
func sqrt(x float64) string { 
	if x < 0 { // once again, no parens needed but brackets yes
		return sqrt(-x) + "i"
	}
	return fmt.Sprint(math.Sqrt(x))
}

func main() {
//variable decleration syntax within function 
	k := 5
//basic hello world
	fmt.Printf("hello, jess\n")
//insert argument where %g is
	fmt.Printf("Now you have %g problems.", math.Sqrt(7))
//imports Pi package
	fmt.Println(math.Pi)
//adds two integers
	fmt.Println(add(42, 13))
//prints using the type variable declaration above
	fmt.Println(jo, mess, love, k)
// for loop
	sum := 0
	for i := 0; i < 10; i++ { // note no parens, but braces always required
		sum += i
	}
	fmt.Println(sum)
//square root function
	fmt.Println(sqrt(2))
//shows reverse hellow world - first print defers
	defer fmt.Println("world")
	fmt.Println("hello")
//In Go, the array length is part of it's type, so they can't be resized
	var a [2]string
	a[0] = "Hello"
	a[1] = "World"
	fmt.Println(a[0], a[1])
	fmt.Println(a)

//Slices provide a flexible view into the elements of the array.  In practice these are more common than arrays. More like a reference to an array.
	primes := [6]int{2, 3, 5, 7, 11, 13}
	var s []int = primes[3:5]
	fmt.Println(s)


}
