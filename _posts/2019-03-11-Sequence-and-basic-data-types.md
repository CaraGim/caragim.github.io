---
layout: post
title: Sequence and basic data types
date: 2019-06-14
excerpt: "how to design and write code professionally in a structured/functional framework."
tags: [sample post, code, highlighting]
comments: true
---



To modify styling and highlight colors edit `/assets/css/syntax.css`.

### Basic Reading Writhing
{% highlight ruby %}
puts "Enter the two number to set a data"
a = gets
b = gets
puts "Outfut is " + a + b
{% endhighlight %}
<p>
<p>
<p>
</p>
### Desk Checking: Bill total<p>
#### Purpose <p>
</p>
Demonstrate an understanding of sequence in programming code and practice checking code.

{% highlight ruby %}
def main
	text = "Calculate the total_price:%.2f\n"
	puts 'Enter the appetizer price (in cents)'
	appetizer_price = gets.chomp.to_i
	puts 'Enter the main price (in cents)'
	  main_price =gets.chomp.to_i
	puts 'Enter the dessert price (in cents)'
	 dessert_price =gets.chomp.to_i
	 total_price =appetizer_price+main_price+dessert_price
	# Note: the following line changes the type of total_price from an integer to a float
	total_price = total_price.to_f / 100
	printf(text,total_price)
	# print out the total_price with 2 decimal places:
	printf('Output the total_price is $%.2f', total_price)
end
{% endhighlight %}
<p>
<p>
<p>
</p>

### Advanced reading and Writing<p>
#### Purpose<p>
Create your own Reading and Writing program using the Ruby language.<p>
##### Instruction<p>
    </p>
 Variables allow you to store values that can change in your program. When you declare a local<p></p>
variable you are telling the computer to create a variable for use within the function or procedure.<p></p>
You must give the variable a name and keep in mind the type of data it will store.<p></p>
The computer will then set aside space for you to store a value for that variable.<p></p>
You can then write values to the variable and read values back.<p></p>
To explore this topic, we will create a Terminal program that will:<p></p>
■ ask the user to enter their name, age, and weight in metres,<p></p>
■ calculate and output the year the user was born, and<p></p>
■ calculate and output the user’s height in inches<p></p>
<p></p>

{% highlight ruby %}
require 'date'
INCHES = 0.393701  # This is a global constant
#Insert the missing code here into the statements below:
#gets
#gets.chomp
#Date.today.year
#year_born.to_i
#gets.to_f

def main
	puts 'What is your name?'
	name =
	puts 'Your name is ' + name + '!'
	puts 'What is your family name?'
	family_name =
	puts 'Your family name is: ' + family_name + '!'
	puts 'What year were you born?'
	year_born =
	# Calculate the users age
	age =
	puts 'So you are ' + age.to_s + ' years old'
	puts 'Enter your height in cms (i.e as a float): '
	value =  # Should this be a float or an Integer? Why?
	value = value * INCHES
	puts 'Your height in inches is: '
	puts value.to_s
	puts 'Finished'
end

main  # call the main procedure
{% endhighlight %}

<p>
<p>
<p>
</p>

