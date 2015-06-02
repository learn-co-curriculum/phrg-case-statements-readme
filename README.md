---
tags: readme
language: ruby
resources: 0
track: web development
topic: ruby
unit: control flow
lesson: case statements
---

# Case Statements


## Example 1: Weather

In this example, we set the `current_weather` to `"raining"`. Next, we use `when` statements to describe a list of possible matches. Since `current_weather === "raining"` we'd expect this code to put `"grab an umbrella"`.

```ruby
current_weather = "raining"
case current_weather
when "sunny"
  puts "grab some sunscreen!"
when "raining"
  puts "grab an umbrella"
when "snowing"
  puts "bundle up"
end
```

## Example 2: Grades

This example requires a basic understanding of `gets.chomp`. It allows us to get a user's input, and use it in our code. [Read more on what it does here.](http://stackoverflow.com/questions/23193813/how-does-gets-and-gets-chomp-in-ruby-work)

Here, we are prompting the user to input a student's grade. Based on that `grade`, the program then prints out the string associated with the matching condition. If the user enters "A", then `grade = "A"`. Since `grade === "A"`, Ruby will print `Well done!` to the screen. 

```ruby
print "Enter your grade: "
grade = gets.chomp
case grade
when "A"
  puts "Well done!"
when "B"
  puts "Try harder!"
when "C"
  puts "You need help!!!"
else
  puts "You just making it up!"
end
```

## Example 3: Names

In this example we are printing out tailored messages depending on certain characteristics of the name. Again, we are using `gets.chomp` to prompt the user for their `name`, but you're a pro at that by now. We're adding another layer of complexity called regular expressions (or regex). Don't be intimidated by their cryptic nature. Regular expressions are just special text strings for pattern matching. Feel free to play around on a regex tester (https://regex101.com/) to see what `/^[qrz].+/i` does. Don't worry if regex is confusing; we'll go into this in more detail later.

```ruby
name = gets.chomp
case name
when "Alice"
  puts "Welcome Alice"
when /^[qrz].+/i 
  puts "Your name begins with Q, R or Z, you're not welcome here!" 
else puts "Welcome stranger!" 
end
```
