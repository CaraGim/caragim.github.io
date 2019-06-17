---
layout: post
title: My Function
date: 2019-03-19
excerpt: "Implement a function and use it to calculate a value based on user input."
tags: [code, function]
comments: true
---
<p>
Procedures are a great tool for capturing the instructions needed to perform a task,<br>
but sometimes you need to be able to capture the instructions needed to calculate a value.<br>
Using functions you can now create artefacts to encapsulate the steps needed to calculate a value.
</p>
### Simple Politic
Use the following instructions to implement a function and use it to calculate a value based on user input.<br>
#### Instruction
<p>
Prompt the user to enter his or her name and birth year.<br>
■ Call a function to calculate how old the user was when Trump was (first) elected President of the USA (you will need to write this function yourself).<br>
■ Print to the terminal the user’s name and age when Trump was elected.<br>
■ Call the read_boolean(prompt) function from input_functions.rb to prompt the user to enter whether he or she is a supporter of Brexit.<br>
■ Print out whether the user supports Brexit or not based on the result of calling the read_boolean(prompt) function.<br>
</p>
 Create the functions for read a user data and response.
{% highlight ruby %}
def get_string prompt
	puts prompt
	value = gets.chomp
end

def get_integer prompt
	value = get_string(prompt)
	value.to_i
end

def get_boolean(name,year_born)
    if year_born.to_i >= YEAR_TRUMP_ELECTED
     puts name + ' is a Brexit supporter'
    else
     puts name + ' is NOT a Brexit supporter' # print "not born"
    end
end
{% endhighlight %}

 Create a function for calculate user age when Trump elected.
{% highlight ruby %}
def calculateUserAge(year_born)
  age_when_trump_elected = YEAR_TRUMP_ELECTED - year_born.to_i
end
{% endhighlight %}

{% highlight ruby %}
def main
  name = get_string('Please enter your name: ')
  year_born = get_integer('What year were you born? ')
  #Replace the line below with a call to your function above:
  calculateUserAge(year_born)
  age_when_trump_elected = calculateUserAge(year_born)
  puts name + ' you were ' + age_when_trump_elected.to_s + ' years old when Trump was elected'
  #Change the following line to call get_boolean
  #prompting the user: 'Are you a Brexit supporter? '
  prompt = 'Are you a Brexit supporter? '
  get_boolean(name,year_born)
end
main
{% endhighlight %}

