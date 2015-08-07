# `case` Statements

##Objectives:

1. Distinguish a `case` statement from other patterns of flow control.
2. Identify when to use a `case` statement.
3. Write a `case` statement

## What is a `case` Statement?

A case statement is a powerful tool to test for certain conditions. They are used to run multiple conditions against one value. There are three basic steps to creating a case statement. First, we'll need a value. Second, we'll want one or more conditions to compare to the value. Third, we'll add the code we want to run if that condition is met. Let's walk through these steps in more detail below.

### Why Use a `case` Statement?

In the previous lessons, we've learned about using `if`, `elsif`, and `else` statements to enact flow control in our programs. Let's look at an example of using `if` statements that would benefit from being refactored to use a `case` statement instead. 

Let's say we have a program that sets a `user` variable equal to a person's name. Our program needs to execute certain code depending on what that person's name is. 

```ruby
name = "Alice"

if name == "Alice"
  puts "Hello, Alice!"
elsif name == "The White Rabbit"
  puts "Don't be late, White Rabbit"
elsif name == "The Mad Hatter"
  puts "Welcome to the tea party, Mad Hatter"
elsif name == "The Queen of Hearts"
  puts "Please don't chop off my head!"
else
  puts "Whoooo are you?"
end 

```

Above we are using many `if` and `elsif` statements to check if the value of our name variable matches a particular string by using the comparative operator (`==`) in each one. 

**Top-Tip:** *Remember that the assignment operator (*`=`*) is distinct from the comparative operator (*`==`*).*

Using `if` and `elsif` statements in this manner creates "code smell"—a piece of code that is needlessly complex or difficult to read. Not only are we using a lot of `if` statements, but we are being repetitive in our use of the comparative operator (`==`). We can eliminate this "code odor" by refactoring our flow control to use a `case` statement instead. The `case` statement will allow us to run multiple conditions against the same value, meaning that we can check the `name` variable against a variety of conditions without repeating our use of the comparative operator (`==`) in each one. 

Let's take a look: 

```ruby
case name 

  when "Alice"
    puts "Hello, Alice!"
  when "The White Rabbit"
    puts "Don't be late, White Rabbit"
  when "The Mad Hatter"
    puts "Welcome to the tea party, Mad Hatter"
  when "The Queen of Hearts"
    puts "Please don't chop off my head!"
  else 
    puts "Whoooo are you?"
end
```

### Writing a `case` Statement

Now that we understand *when* to use a `case` statement in place of a series of `if` and `elsif` statements, let's look at *how* to build a `case` statement from scratch. 

#### Step 1: Create a Value

A case statement starts with the `case` keyword followed by a value to test.

```ruby
case "friendly_greeting"
# ...
end
```

#### Step 2: Create the Conditions

Next, the `when` keyword is followed by a condition.

```ruby
case "friendly_greeting"
  when "unfriendly_greeting"
    #...
  when "friendly_greeting"
    #...
end
```

#### Step 3: Add the Code

The functionality that we wish to happen when the condition is met is placed on an indented line directly under the `when` line. Let's define the behavior:

```ruby
case "friendly_greeting"
  when "unfriendly_greeting"
    puts "What do you want!?"
  when "friendly_greeting"
    puts "Hi! How are you?"
end
```

##### Advanced: How does it work?

Under the hood, `case` statements actually evaluate their `when` conditionals by implicitly using the "case equality operator"; the case equality operator is otherwise represented by `===` ("threequals") sign. While `case` can be used to replace the comparison operator in a situation like the first example in this reading, it's doing something slightly different. [Read more about === here.](http://stackoverflow.com/questions/3422223/vs-in-ruby?lq=1)

Similar to the comparison operations above, the `when` statement evaluates to a boolean value by using the `case` value at the start of the `case` statement and the value following the `when` keyword. If this `when` condition evaluates to `false`, then the indented code beneath that condition is skipped; if it evaluates to `true`, then the indented code beneath it is executed.

In the above case, Ruby compares the `case` value to the two `when` conditions; `"friendly_greeting" === "unfriendly_greeting"` is `false`, so `puts "What do you want!?"` is *not* run; however, `"friendly_greeting" === "friendly_greeting"` is `true`, so `puts "Hi! How are you?"` *is* run.

It is not necessary at this point to understand the distinction between the comparative operator (`==`) and the case comparison operator (`===`). Just realize that there *is* a distinction, even though the usages relevant to you right now will be similar.

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

Here, we are prompting the user to input a student's grade. Based on that `grade`, the program then prints out the string associated with the matching condition. If the user enters "A", then `grade = "A"`. Since `grade === "A"`, Ruby will print `Good jorb, Homestar!` to the screen. 

```ruby
print "Enter your grade: "
grade = gets.chomp

case grade
  when "A"
    puts "Good jorb, Homestar!"
  when "B"
    puts "You can totally do better!"
  when "C"
    puts "Find a mentor to help you!"
  else
    puts "You're just making that up!"
end
```
