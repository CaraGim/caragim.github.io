---
layout: post
title: Name tester
date: 2019-03-21
excerpt: "Create a program that tests a user's name and echoes a custom message."
tags: [code, function]
comments: true
---
<p>
  Control flow enables you to easily add conditions and loops to your programs.<br>
In this task you will create a small program that uses conditions and<br>
loops to output custom messages to users.
</p>

### Name Tester
#### Instruction
■It reads a name from the user, and displays back a message.<br>
■ Check if the name entered is your name.<br>
■ If the name is your name or your tutor’s name output the message 'Awesome name!'<br>
■ Otherwise output the silly name message:<br>
 ▼Design the process
{% highlight ruby %}
def main
 name = readName('Enter yours or tutors name: ')
 boolean(name)
end
main
{% endhighlight %}
 ▼Create the funtion for read user name
{% highlight ruby %}
def readName(prompt)
 puts prompt
 value = gets.chomp
end
{% endhighlight %}
 ▼Create the function for verifying data
{% highlight ruby %}
def boolean(prompt)
   if (prompt == 'Chaeeun Gim' || prompt == 'William Sun' )
     puts "<" + prompt + ">" + ' is an awesome name!'
   else
     puts "<" + prompt + ">" + ' is a'
     i = 0
     while i < 60
          print 'silly'
          i += i
     end
     puts "\n" + 'name!'
   end
end
{% endhighlight %}
