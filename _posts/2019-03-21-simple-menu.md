---
layout: post
title: Simple Menu
date: 2019-03-21
excerpt: "Create a program that implements a basic menu system."
tags: [code, function]
comments: true
---

<p>
  In this task you combine control flow with modularization to create the basis of a menu system
for a text-based (terminal based) Music player.
</p>
### Simple Menu
#### purpose
 Learn to combine control flow and modularisation.
 <p>
#### Instruction
■ A repeat-until loop with the following:<br>
■ Display the sub-menu options and prompt the user to select one<br>
■ Read in the user selection and then use a case statement to<br>
call a procedure that corresponds to the selection (or leave the loop if they chose exit)<br>
■ The called procedure should display a message to user about the option.<br>
You do not need to implement the procedure at this stage, <br>
just leave it as a ‘stub’ that displays a message.
</p>
<br>
 ▼ Create the function for displaying main menu.
{% highlight ruby %}
def main()
  finished = false
  begin
    puts 'Main Menu: Enter your selection: '
    puts '1 To Enter or Update Album'
    puts '2 To Play existing Album'
    puts '3 Exit'
    choice = read_integer_in_range("Please enter your choice:", 1,3)
    case choice
    when 1
      puts 'You selected for looking for maintain albums'
      maintain_albums()
    when 2
      play_existing_album()
    when 3
      puts "good bye!"
      finished == true
    else
      puts 'Please select again'
    
    end until finished == true
  end
end

main()
{% endhighlight %}
