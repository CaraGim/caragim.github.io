---
layout: post
title: File Handling
date: 2019-04-02
excerpt: "Modify a simple Ruby program that reads and writes from a file to use loops."
tags: [code, function]
comments: true
---

### File Handling
#### Instruction

Files allow you to store data persistently. <br>
In this task you will write a simple file reading program to read multiple lines using a loop printing each line read to the terminal screen.<br>
To explore this topic, we will modify a Terminal program that will, when complete:<br>
■ Open a file and write a number of records to the file. Close the file.<br>
■ Open a file and loop according to the number of records to read in each record.<br>
■ Print each record that is read (as they are read).<br>
■ Use the code provided (from this task’s resources in Doubtfire) to get started, using this code complete the following:

//<div style="padding-left: 40px; text-indent: -40px">
<div style="width: 200px; padding-left: 40px; text-indent: -40px">

1. Open and look at the code in the Resources for the basic code for reading and writing<br>
the records from files. The functionality of this code is basically correct, but the code can<br>
be improved in design and implementation, these are the modifications you will make.<br>
2. Make the following modifications the basic_read_write.rb program so that it:<br>
• Uses a loop in read_data_from_file, with the loop controlled by the number at the start of the file.<br>
• Improve the functional decomposition by removing as many lines of code from main as possible, yet retaining good structure.<br>
</div>


1. Open a File and start to write the data.
{% highlight ruby %}
def writingfileConfim()
  a_file = File.new("listOfName.txt", "w") 
  if a_file  #if nil this test will be false
    write_data_to_file(a_file)
    a_file.close
  else
    puts "Unable to open file to write!"
  end
end
{% endhighlight %}

2. Writes the number of lines then each line as a string.
{% highlight ruby %}
 def write_data_to_file(a_file)
  count = a_file.puts.to_i
  #a_file.puts('5')
  for count in 0..0
   a_file.puts('Fred')
   a_file.puts('Sam')
   a_file.puts('Jill')
   a_file.puts('Jenny')
   a_file.puts('Zorro')
  end
{% endhighlight %}

3. Open a File for reading data.
{% highlight ruby %}
def readingFileConfirm()
  a_file = File.new("listOfName.txt", "r")
  if a_file  #if nil this test will be false
    read_data_from_file(a_file)
    a_file.close
  else
    puts "Unable to open file to read!"
  end
end
{% endhighlight %}


4. Reads in each line. It uses a loop which repeats according to the number or lines in the File<br>which is given in the first line of th File.
{% highlight ruby %}
 def read_data_from_file(a_file)
  count = a_file.gets.to_i # count = 0
  for count in 0..0
    puts count.to_s #head number
    index = 0 #sub number
    while (index <= 4 )
     puts "#{index}." + a_file.gets 
     index += 1
    end
    count += 1
  end
end
{% endhighlight %}

5. Excute
{% highlight ruby %}
def main
  writingfileConfim()
  readingFileConfirm()
end
{% endhighlight %}



