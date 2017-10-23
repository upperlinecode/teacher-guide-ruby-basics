# Intro to Ruby

#### Sequence

1. [Setting Up](#setting-up)
2. [Hello World](#hello-world)
3. [Math](#math)
4. [Variables and Interpolation](#variables-and-interpolation)
5. [User Input](#user-input)
6. [Control Flow](#control-flow)
7. [Datatype Conversion](#datatype-conversion)

## Setting up

Students will benefit from a walkthrough, as most just started interacting with the command line for the first time this morning.

```bash
mkdir day-one
cd day-one
touch hello.rb
```

CFU by having students identify that their prompt ends in `day-one`, and by identifying a hello.rb file on the left side of the screen.  

This lesson introduces a lot of really foundational vocabulary words. This is a CRITICAL time to make a **datatypes anchor chart**, and include integers, floats, strings, and booleans. Leave room for Symbols, which will come up on day 3 when we cover hashes.

## Hello World

In the ruby file:
```ruby
puts "hello world!"
```

Name that `puts` stands for "put string" and explain that anything in quotes is a **String** of characters. A string essentially represents a word or phrase.

In the console:
```bash
ruby hello.rb
```

#### Playtime

* Print out a 5-sentence story with 5 different statements
* Try `print` instead of `puts`
* Google the phrase "ASCII-art" and try to make your program print it out to the console

## Math

In the console:
```bash
touch math.rb
```

In the ruby file:
```ruby
puts("4" + "3")
puts(4 + 3)
puts(4.0 + 3.0)
```

Name the datatypes Int and Float, but avoid explaining the difference.
Ask students to make a prediction about what each line will print before moving on.

In the console:
```bash
ruby math.rb
```

#### Playtime

* Ask students to try these operators and see if they can figure out what each does.
* Also ask them if they can figure out the difference between 4 and 4.0 and the way they behave with each of them.
    * `+`, `-`, `*`
    * `/`, `**`
    * `%`
* Ask students whether it's possible to mix datatypes, like `puts("hello" * 3)` or `puts(4 / 3.0)`
*Note: this practice section may be easier to run in a REPL (like irb) in the console. If you're interested, just type irb in the console. Type "exit" to close irb.*

#### Takeaways

* STRINGS - explain what a string is and why it's used
* STRINGS - create strings using double quotes
* PUTS - Explain what a puts statement is and what it's used for
* INT - explain what an integer is and why it's used
* INT - use common mathematical operations with integers
* INT - understand that ruby rounds down when doing math with integers
* FLT - explain what a float is and why it's used
* FLT - understand that math with floats produces floats and math with integers produces integers
* FLT - use common mathematical operations on floats

## Variables and Interpolation

In the console:
```bash
touch greet.rb
```

In the ruby file:
```ruby
name = "Lauren"

puts "Good morning #{name}!"
```

Identify that the word "name" isn't a string, since it doesn't have quotes around it. Identify that it is a **variable** that *contains* a string.
Ask students to predict what will be printed to the console.

In the console:
```bash
ruby greet.rb
```

Ask students to explain what happened. Identify that this method of "filling in the blank" with the contents of a variable is called **interpolation**. Explain that this is one of two ways to do this. The other is called **concatenation** which actually saw earlier when you wrote `puts("4" + "3")`.

In the ruby file:
```ruby
name = "Lauren"
name2 = "Manuel"

puts "Good morning #{name}!"
puts "Good morning " + name2 + "!"
```

Stop and ask students whether they prefer concatenation or interpolation and have them explain why. 

#### Playtime

* Ask students to add a variable called age that has a string inside of it and try interpolating (or concatenating) TWO variables into one string.

#### Built-in methods

In the ruby file:
```ruby
name = "Lauren"

puts "Good morning #{name}!"
puts "Your name has #{name.length} letters in it!"
```

* Ask students to predict what will be printed. 

#### Playtime

* Ask students to change the string "Lauren" to another name.
* Ask them what will be printed if they change Lauren's name to their own. Let them test it out. Explain that this is a built-in string method, and that it's **called** on a string using this dot syntax.
* Ask students why it's better to have the computer compute the length of Lauren's name rather than just hard-coding in the number 6.
* Let students know there are LOTS of string methods. List out a few, such as .upcase, .downcase, .capitalize, .swapcase, and let students predict how they will manipulate text and then test them out in their own code.
* Prompt students to Google "Ruby string methods," and take an opportunity to look at Ruby Docs together, locating the variety of string methods that exist and playing with any that look interesting.


#### Takeaways

* STRINGS/VARIABLES - interpolate a variable or a method within a string
* VAR - use a variable in place of a piece of data
* STRINGS - use common string methods

## Break for Labs
Students now have everything they need to do the John Jacob Jingleheimerschmidt lab.
Students who progress quickly through that can move on to the DNA lab.
Neither requires user input or control flow.  

## User Input

Continue modifying the greet program. ID that when we write a program, we won't know the user's name.

In the ruby file:
```ruby
puts "What is your name?"
name = gets.chomp

puts "Greetings, #{name}! Welcome to the program."
```

Ask students to predict what will happen when this program is run.
Identify that "gets" stands for "get string".
*If a student asks about the .chomp method, invite them to try it out and see if they can figure out what it does.*

In the console:
```bash
ruby greet.rb
```

#### Takeaways

* GETS - take in user input using the gets method
* VAR - use correct syntax in naming variables

## Control Flow

#### Basic control flow

In the ruby file:
```ruby
puts "What is your name?"
name = gets.chomp

if name == "Beyonce"
  puts "Welcome, queen B."
else
  puts "Greetings, #{name}! Welcome to the program."
end
```

Before running, ask students to predict what will happen if the user says their name is Beyonce. Then ask what will happen if the user gives a different name. Be prepared for students to notice that 'beyonce' with a lowercase b will not work.

Ask students to try running this program to get both results. Preface this with the fact that about HALF the students will get errors.

#### Compound operators and branching if statements

In the ruby file:
```ruby
puts "What is your name?"
name = gets.chomp
puts "Please enter your password."
password = gets.chomp

if name == "Beyonce" && password == "Lemonade1"
  puts "Welcome, queen B."
elsif password != "Lemonade1"
  puts "WARNING. Incorrect password"
else
  puts "Greetings, #{name}! Welcome to the program."
end
```

Ask students what the password is for the program. Ask students to run this program with combinations of answers to get all three results. Explain that they can expect errors, and celebrate those errors as learning opportunities.

#### Takeaways

* CONDITIONALS - Explain what an if statement is and why it's used
* CONDITIONALS - Implement an if statement with 1, 2, and 3+ branches
* CONDITIONALS - Use comparison operators in a conditional statement

## Datatype Conversion

Challenge students to build a program that does all of the following:
* Asks the user for their age
* Stores that age in a variable
* Prints out whether or not they are old enough to vote
* Stretch - also checks whether or not they are old enough to drive, rent a car, or get a senior discount

In the console:
```bash
touch ageCheck.rb
```

In the ruby file:
```ruby
puts "How old are you?"
age = gets.chomp

if age >= 18
  puts "You're old enough to vote!"
else
  puts "You're not old enough to vote."
end
```

In the console:
```bash
ruby ageCheck.rb
```

We're intentionally triggering an error: `comparison of String with 18 failed`. Talk with students about the importance of *reading* their errors, not just freaking out. Whether students arrive at the correct conclusion or not, make sure to direct their thinking by asking the following questions:
* What's the difference between `"18"` and `18`?
* What does `gets` stand for?
* Optional: Ask students which is greater, "green" or "brown" to help them see that using a greater-than operator on strings makes no sense.

In the ruby file:
```ruby
puts "How old are you?"
age = gets.chomp # Read this as "Set age equal to whatever string the user types."
age = age.to_i # We reassign the variable here information here.
# In essence, "Set age equal to an integer expression of whatever the user typed."

if age >= 18
  puts "You're old enough to vote!"
else
  puts "You're not old enough to vote."
end
```

#### Playtime

Stretch challenges / lab time:
* Include other age cutoffs for activities like driving, renting a car, or retiring.
* Go back to the greeter and add code to ask for the user's age.
    * Write code to respond if Beyonce's age is incorrect.
* Go back to the greeter and add to the user base by making sure it can greet Jackie Chan, Will Smith and a few other celebrities. Consider giving them unique passwords.
* Invite them to go back and finish any of the earlier labs that were giving them trouble.

#### Takeaways

* GENERAL RUBY - explain that an error will stop the execution of ruby code
* GENERAL RUBY - Students understand that errors provide useful information about what's going wrong
* VAR - reassign the value of a variable
* INT - use typical methods like to_f and to_s to mutate integers
* FLT - use typical methods like to_i and to_s to mutate float
