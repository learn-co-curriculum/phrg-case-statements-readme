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

See how we can do weather in ruby.

```ruby
weather = "raining"
case weather
when "sunny"
  puts "grab some sunscreen!"
when "raining"
  puts "grab an umbrella"
when "snowing"
  puts "bundle up"
end
```

## Example 2: Grades

```ruby
print "Enter your grade: "
grade = gets.chomp
case grade
when "A"
  puts 'Well done!'
when "B"
  puts 'Try harder!'
when "C"
  puts 'You need help!!!'
else
  puts "You just making it up!"
end
```

## Example 3: Names

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
