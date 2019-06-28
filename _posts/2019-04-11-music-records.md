---
layout: post
title: Music Records
date: 2019-04-11
excerpt: "Produce a simple Ruby program which reads and writes custom data types (records)."
tags: [code, function]
comments: true
---

###Music Records
Produce a simple Ruby program which reads and writes custom data types (records).
####Instruction
■ Add the missing code to the function/method read_album()<br>
■ Add the missing code to the procedure/method print_album()<br>
■ Optional: Add an initialize() method to the Album class/record definition.<br>
<br>
A.<br>Set the class and initialize the elements.
{% highlight ruby %}
require './input_functions'

module Genre
  Null,POP, CLASSIC, JAZZ, ROCK = *1..4
end
$genre_names = ['Null', 'Pop', 'Classic', 'Jazz', 'Rock']

class Album
	attr_accessor :title, :artist, :genre
	def initialize (title, artist, genre)
        @title = title
        @artist = artist
        @genre = genre
	end
end
{% endhighlight %}

B.<br>
Reads in and returns a single album from the given file, with all its tracks.<br>
{% highlight ruby %}
def read_album
 puts "【Create Album】"
 puts "Enter album title"
  album_title = gets.chomp
  puts "Enter album artist"
  album_artist = gets.chomp
  album_genre = read_integer_in_range("Enter the Genre number between 1 - 4", 1, 4)
  album = Album.new(album_title,album_artist,album_genre)
  return album
end
{% endhighlight %}

C.<br>Takes a single album and prints it to the terminal.<br>
{% highlight ruby %}
def print_album album
 puts('Album information is: ')
    # insert lines here
    puts 'Title is 【' + album.title.to_s + "】"
  
    puts 'Artist is 【' + album.artist.to_s + "】"
    
    puts "Genre is 【#{album.genre}. #{Genre.constants[album.genre]}】" #?
    #$genre_names[album.genre]
end
{% endhighlight %}

D.<br>Reads in an array of albums from a file and then prints all the albums in the array to the terminal
{% highlight ruby %}
def main
  album = read_album()
	print_album(album)
end
main
{% endhighlight %}

E.<br>Additional function for "read_album()"function.
{% highlight ruby %}
def read_integer_in_range(prompt, min, max)
	value = read_integer(prompt)
	while (value < min or value > max)
		value = read_integer(prompt);
	end
	value
end
{% endhighlight %}




