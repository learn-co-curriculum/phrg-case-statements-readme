# Case Statements

##Objectives:

1. Understand what a case statement is and how it works to enact flow control
2. Understand when to use a case statement
3. Be able to write a case statement

##What is a Case Statement?

A case statement is a powerful tool to test for certain conditions. They are used to run multiple conditions against one value. There are three basic steps to creating a Case Statement. First, we'll need a value. Second, we'll want one or more conditions to compare to the value. Third, we'll add the code we want to run if that condion is met. Let's walk through these steps in more detail below.

### Why Use a Case Statement?

In the previous lesson, we learned about use `if/elsif/else` statements to enact flow control in our programs. Let's look at an example of using if statements that would benefit from being refactored to use case statements instead. 

Let's say we have a program that sets a `user` variable equal to a person's name. Our program needs to execute certain code depending on what the person's name is. 

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

Above we are using many `if/elsif` statements to check if the value of our name variable matches a particular string, using the `==` comparative operator. 

**Remember that the single `=` sets a variable equal to a value but the double `==` checks for equality* 

The code above smells. Not only are we using a lot of if statements, we are being repetitive in our use of the `==`. Lucky for us there is a way to reduce this repetition––the case statement. The case statement will allow us to run multiple conditions against the same value, i.e. to check if the `name` variable is equal to a variety of conditions, without repeating our use of the `==` operator. 

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

Now that we understand when to use a case statement of a series of if/elsif statements, let's look at how to build a case statement ourselvs. 

### Step 1: Create a Value
A case statement starts with the `case` keyword followed by a value to test.

```ruby
case "friendly_greeting"
# ...
end
```
###Step 2: Create the Conditions
Next, the `when` keyword is followed by a condition.

```ruby
case "friendly_greeting"
  when "unfriendly_greeting"
    #...
  when "friendly_greeting"
    #...
end
```
###Step 3: Add the Code
What do you want to happen when the value and condition match? The functionality you wish to have when the condition is met is placed on an indented line directly under the `when` line. Now it's time to add that code.

```ruby
case "friendly_greeting"
  when "unfriendly_greeting"
    puts "What do you want!?"
  when "friendly_greeting"
    puts "Hi! How are you?"
end
```

**Bonus: How does it work?**

The value and the condition are compared using the triple equals operator `===` (i.e. value === condition). [Read more about === here.](http://stackoverflow.com/questions/3422223/vs-in-ruby?lq=1) The result of the comparison is a boolean value (`true` or `false`). If the value and condition evaluates to `false`, the indented code beneath that condition is skipped. If it evaluates to `true`, the indented code beneath it is executed.

In the above case, Ruby compares the `case` value to the two `when` conditions. `"friendly_greeting" === "unfriendly_greeting"` is `false`, so `puts "What do you want!?"` is not run. `"friendly_greeting" === "friendly_greeting"` is `true`, so `puts "Hi! How are you?"` is run.

Don't worry about understanding the `===` operator. As long you understand how your case statement will function, you're good to go!

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
