---
layout: post
title: Using Functions
date: 2019-03-14
excerpt: "how to design and write code professionally in a structured/functional framework."
tags: [sample post, code, highlighting]
comments: true
---

### Hello User
<p></p>
#### Instruction
<p>
■ ask the user to enter their name, age, and the current year, <br>
■ calculate the year the user was born, and<br>
■ output a greeting message.<br>
</p>

{% highlight ruby %}
require 'date'
require './input_functions'

INCHES = 0.393701  # This is a global constant

#Insert into the following your hello_user code
#from task 1.3P and modify it to use the functions
#in my_functions

def printAnswer(displayPrompt,prompt)
   prompt = prompt + "!"
   puts displayPrompt + prompt
end

def main
   name = read_string( "Please enter your name: ")
   displayPrompt = printAnswer("Your name is: ",name)
   name = read_string("what is your family name:  ")
   displayPrompt = printAnswer("Your family name is: ",name)

   userAge = read_string("What year were you born?")
   userAge = Date.today.year - userAge.to_i
   puts "you are " + userAge.to_s + " years old"
 
   userHeight = read_string("Enter your height in cms (i.e as a float): ")
   userHeight = userHeight.to_f * INCHES
   puts 'Your height in inches is: ' + userHeight.to_s

   read_boolean("Do you want to continue?")

end

main
{% endhighlight %}

##### input function code
<p>
Hello User code call the function of 'input_function_code'. 
<br>The codes are:
{% highlight ruby %}
def read_string prompt
	puts prompt
   value = gets.chomp
end

def read_boolean prompt
    #puts prompt
    value = read_string(prompt)
    case value
	when 'y', 'yes', 'Yes', 'YES'
		puts 'Ok, lets continue'
	else
		puts 'ok, goodbye'
	end
end
{% endhighlight %}
</p>


